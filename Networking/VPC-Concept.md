Quiz
1. Your startup has three VPCs: VPC A (Frontend), VPC B (Shared Services), and VPC C (Database). You have configured a VPC peering connection between VPC A and VPC B, and another between VPC B and VPC C. An app instance in VPC A tries to connect to the database in VPC C, but the connection times out. You confirmed that VPC B can talk to both VPC A and VPC C. What is causing this connection failure?

```
Answer -> VPC peering is non-transitive, so traffic from VPC A cannot pass through VPC B to reach VPC C.

This is the core rule of VPC peering. Peering connections only allow direct, one-to-one communication. You cannot use a middle VPC as a transit hop to reach another VPC. To fix this, you must peer VPC A directly to VPC C.
```

2.Your startup is growing fast. You now have 10 VPCs that all need to talk directly to each other. You decide to use VPC peering to connect them in a full mesh. How many total peering connections do you need to create and manage?

Answer

# VPC Peering Full Mesh Calculation

Your startup has **10 VPCs** and each VPC must connect directly to every other VPC using **VPC Peering**.

## Formula

For a full mesh network:

connections = n(n-1)/2

Where:

- `n` = number of VPCs
- `n = 10`

## Calculation

10(10-1)/2

10(9)/2

90/2 = 45

## Final Answer

✅ Total VPC Peering Connections Required: **45**

---

## Important Note

A full mesh architecture grows rapidly as the number of VPCs increases.

Examples:

| VPCs | Connections |
|------|-------------|
| 5    | 10 |
| 10   | 45 |
| 20   | 190 |
| 50   | 1225 |

Because of this, large AWS environments usually prefer:

- AWS Transit Gateway
- Hub-and-Spoke Networking
- Shared Services VPC Architecture

