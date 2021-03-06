# External DNS Component

![Component version](https://img.shields.io/badge/dynamic/yaml?color=blue&label=component+version&query=$.entries.external-dns[0].version&url=https%3A%2F%2Frepository.platform.karavel.io%2Funstable%2Findex.yaml&style=for-the-badge)
[![External DNS version](https://img.shields.io/badge/dynamic/yaml?color=blue&label=external-dns+version&query=$.entries.external-dns[0].appVersion&url=https%3A%2F%2Frepository.platform.karavel.io%2Funstable%2Findex.yaml&style=for-the-badge)](https://github.com/kubernetes-sigs/external-dns)
[Documentation](https://platform.karavel.io/components/external-dns)

## Overview

ExternalDNS synchronizes exposed Kubernetes Services and Ingresses with DNS providers. In a dynamic and elastic
environment like Kubernetes, services come and go in the blink of an eye. Developers may want deploy a new service to
the public and need a DNS record to route traffic into the cluster. Having to ask an administrator to manually configure
the DNS provider can be tedious and a waste of time, especially in large organizations. External DNS bridges the gap
between Kubernetes network objects, like Service and Ingress definitions, and configure the upstream DNS provider
accordingly, taking care of creating, updating or deleting records as needed.

## License

The External DNS Component is licensed under the [Apache 2.0 license](LICENSE).

The Karavel Container Platform is licensed under
the [Apache 2.0 license](https://github.com/karavel-io/platform/blob/main/LICENSE).
