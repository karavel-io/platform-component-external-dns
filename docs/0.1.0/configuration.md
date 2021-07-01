# Configuration

```hcl
component "external-dns" {
  version = "0.1.0"
  namespace = "external-dns"

  # Params default values

  # when configured with a base domain, external-dns will ignore requests that are not children domains
  domainFilter = ""
  
  # Upstream DNS provider to configure
  # required, must be one of 'cloudflare', 'route53'
  provider = "" 
  
  cloudflare = {
    # Enable or disable the Cloudflare Proxy on managed records. Can be overridden on a per-object basis
    proxied = false
    
    # Restrict to domains in a specific Cloudflare Zone. Optional
    zoneId = ""
    
    # ExternalSecret object reference to a secrets holding the Cloudflare API Token
    secret = {
      # Must be one of the services configured in the External Secrets component
      backend = "secretsManager"
      
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
}
```
