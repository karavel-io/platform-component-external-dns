# Configuration

```hcl
component "external-dns" {
  version = "0.2.0"
  namespace = "external-dns" # optional

  # Params default values

  # when configured with a base domain, external-dns will ignore requests that are not children domains
  domainFilter = ""

  # Upstream DNS provider to configure
  # required, must be one of 'cloudflare', 'route53', 'pdns'
  provider = ""

  cloudflare = {
    # Enable or disable the Cloudflare Proxy on managed records. Can be overridden on a per-object basis
    proxied = false

    # Restrict to domains in a specific Cloudflare Zone. Optional
    zoneId = ""

    # ExternalSecret object reference to a secret holding the Cloudflare API Token
    secret = {
      store = {
        name = "default"
        kind = "ClusterSecretStore"
      }

      # Backend-specific key for the target secret
      key = ""

      # Optional nested property inside the upstream secret
      property = ""
    }
  }

  route53 = {
    # Only look at zone of this type (values can be 'public', 'private' or empty for both)
    zoneType = ""
    # Restrict to domains in a specific Route53 Zone. Optional
    zoneId = ""
    # Configure when deployed on EKS or other platforms with IAM Roles for Service Accounts
    eksRole = ""
    # Configure when deployed on AWS with KIAM
    iamRole = ""
  }

  pdns = {
    apiUrl = ""
    # ExternalSecret object reference to a secret holding the PowerDNS API key
    apiKeySecret = {
      store = {
        name = "default"
        kind = "ClusterSecretStore"
      }
      # Backend-specific key for the target secret
      key = ""
      # Optional nested property inside the upstream secret
      property = ""
    }
  }
}
```

## Route53

To use Route53, a valid IAM role must be created with the following policies:

### For the hosted zone only:

- `route53:ChangeResourceRecordSets`

### For everything (`"*"`):

- `route53:ListHostedZones`
- `route53:ListResourceRecordSets`
