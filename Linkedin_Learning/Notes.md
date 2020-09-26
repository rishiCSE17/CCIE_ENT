# Enterprise Architecture 
## Tier-2 vs. Tier-3 Design
### 3-tier 
* __Core layer:__ Speed, connecting WAN,  Hybrid (Star + Mesh) topology
* __Distribution layer:__ Interconnecting ASWs, Redundancy, Hybrid (Star + Mesh) topology 
* __Access layer:__ Connecting end devices, APs, per-floor.  Star topology

###2-tier
For SOHO or SME implementations
* __Collapsed Core layer__:  Distribution + Core 
* __Access layer__: Access layer 

For DC environment 
* __Spine layer__: full-mesh connection to leaf switches
* __Leaf layer__: connects to every spline switch,each spine swich is one hop away from another, the full implementaion turns 
into a single logical switch  

## On-prem vs Cloud
Internet is untrusted therefore use VPN to interconnect between sites or 
use a private connection over wan using MPLS/Metro-Ethernet etc.

| Cloud | On-prem |
|--- |---|
| no maintain local power supply | needs to have them |
| pay on demand, no physical purchase | needs to buy physical hardware |
| difficult to meet compliance requirement | easy to meet |
| UX depends on internet | better UX |

most of the cases a __Hybrid__ (Cloud + On-prem + Multi-cloud) deployment is used 

## Fabric Capacity Planing 
* Used in DC fabric with Spine-Leaf setup
* How much BW does a Spine switch need to meet requirement ?
* Basic Question?
    1. How much data we need to push through ? (Use historical data + employee exp)
    2. What is the hardware capacity? 
    3. What is the need forecasted for the future? 
* Formula: $BW_{cap} = SW_{cap} N_{io}+\frac{N_{se}}{2}$

