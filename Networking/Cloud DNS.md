# Google Cloud Domain Name System

[Google Cloud DNS](https://cloud.google.com/dns/overview) is a high-performance, resilient, global Domain Name System (DNS) service that publishes your domain names to the global DNS in a cost-effective way.

## Features

* Uses anycast to route requests to the nearest location.
* Supports modern DNS standards.
* 100% SLA.
* DNS forwarding allows your DNS queries to be passed to an on-premis DNS server if you are using Cloud VPN or Interconnect
* DNSSEC is DNS security, which provides strong authentication, designed to prevent spoofing and cache possoning
* DNS managed zone can be public or private
* Public zone are accessible from hte internet and provide name servers that responde to queries from any source
* Private zones provide name services to your GCP resources, such as VMs and load balancers. Responds only to queries originate from resources in the same project as the zone
