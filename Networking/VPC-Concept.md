Quiz
1. Your startup has three VPCs: VPC A (Frontend), VPC B (Shared Services), and VPC C (Database). You have configured a VPC peering connection between VPC A and VPC B, and another between VPC B and VPC C. An app instance in VPC A tries to connect to the database in VPC C, but the connection times out. You confirmed that VPC B can talk to both VPC A and VPC C. What is causing this connection failure?

```
Answer -> VPC peering is non-transitive, so traffic from VPC A cannot pass through VPC B to reach VPC C.

This is the core rule of VPC peering. Peering connections only allow direct, one-to-one communication. You cannot use a middle VPC as a transit hop to reach another VPC. To fix this, you must peer VPC A directly to VPC C.
```
