# Route53

## Hosted Zones
- Simple routing
- Weighted
- Geolocation
- Failover
- Multivale (Round Robin)

## Health Checks 
Will check for string in response) based on: 
- time
- endpoing
- ip
- name/path

## How can you secure Route53?

- **DNSSEC** (Domain Name System Security Extensions): DNSSEC is a security feature that helps ensure the integrity and authenticity of DNS data. Route 53 supports DNSSEC, allowing you to sign your domain's DNS records and verify their authenticity through digital signatures.
- **DNS Firewall**: DNS Firewall in Route 53 allows you to set up rules to block DNS queries to known malicious domains or IP addresses. This helps in preventing access to malicious content and mitigating potential DNS-based attacks.
- **Health Checks**: Route 53 offers health checks to monitor the health and availability of your resources. You can configure health checks for your endpoints and define the criteria for determining their availability. This helps in detecting and responding to any issues or outages affecting your resources.
- **Traffic Flow**: Traffic Flow in Route 53 allows you to configure advanced traffic routing policies for your domain. It includes features such as geolocation routing, latency-based routing, and weighted round-robin routing. These features help distribute traffic efficiently and provide resilience against DDoS (Distributed Denial of Service) attacks.
- **VPC Associatio**n: Route 53 supports associating your DNS records with Virtual Private Cloud (VPC) resources. By associating records with VPCs, you can control access to your resources within your private network and enhance the security of your DNS infrastructure.
