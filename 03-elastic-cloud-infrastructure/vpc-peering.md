# Shared VPC and VPC Peering

## Shared VPC

- Allows an organization to connect resources from multiple projects to a common VPC network
- Allows the resources to communicate using internal IPs from the shared network

## VPC Peering

- Allows private connectivity across VPC networks regardless if they belong to the same project or same organization
- Each VPC network may have its own firewall rules
- In order for VPC peering to be established the producer network admin needs to peer the producer network with the consumer network and vice-versa
- When both peering connections are created, the peering session becomes active and routes are exchanged

| Feature                   | VPC Sharing                                            | VPC Peering                                           |
|---------------------------|--------------------------------------------------------|------------------------------------------------------|
| Purpose                   | Enables sharing of VPC networks across projects within the same organization | Establishes direct connectivity between VPC networks |
| Interconnectivity         | Allows resources in different projects to communicate with each other using shared VPC | Enables communication between separate VPC networks in the same or different projects |
| Ownership                 | The VPC owner can share the VPC network with other projects within the same organization | Each VPC network retains its ownership and control over resources |
| Permissions               | The VPC owner can grant IAM permissions to other projects to use the shared VPC | Requires permissions to be configured in both VPC networks for peering |
| Subnet Configuration      | Shared VPC has a single set of subnets that can be accessed by attached projects | Each VPC network has its own set of subnets with unique CIDR ranges |
| Routing Configuration     | Centralized routing configuration managed by the VPC owner | Requires route configuration in each VPC network for peering |
| Communication Security    | Traffic between resources within the shared VPC remains within Google's infrastructure | Traffic between peered VPC networks is encrypted and traverses Google's backbone network |
| Use Cases                 | Ideal for centralizing network administration and resource management | Suitable for scenarios requiring direct communication between separate VPC networks |
| Network Isolation         | Projects attached to the shared VPC can access resources within the VPC but are isolated from each other | Peered VPC networks can communicate with each other, but resources are still isolated within their respective networks |
| Project Structure         | Requires organization-level hierarchy with projects under the same organization | Can be established between VPC networks within the same or different projects, with appropriate permissions |
