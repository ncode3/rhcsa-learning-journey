# How Cloud Providers Make Money: Overcommitment Economics

## The Secret

Cloud providers (AWS, Azure, GCP) achieve 70-80% gross margins by **selling more resources than they physically have**.

This isn't fraud - it's smart business based on utilization patterns.

## The Math

### Physical Server Example
```
Hardware: 48 CPU cores, 384 GB RAM
Cost: ~$580/month
  - Hardware depreciation: $417/month
  - Power: $36.50/month
  - Cooling: $25/month
  - Network: $20/month
  - Labor: $50/month
  - Facility: $30/month
```

### What AWS Sells (Conservative)
```
10× m5.xlarge instances (4 vCPU, 16 GB each)
- Total sold: 40 vCPUs on 48 physical cores
- Revenue: $140/month × 10 = $1,400/month
- Profit: $820/month (59% margin)
```

### What AWS Actually Does (Aggressive)
```
Physical: 48 cores
Sold: 192-288 vCPUs (4-6:1 overcommit ratio)
Why it works: VMs idle 80-95% of time
Revenue: $2,000-3,000/month
Profit: $1,420-2,420/month (71-81% margin)
```

## Why Overcommitment Works

### CPU Overcommitment
```
Conservative: 2-3:1 (enterprise production)
Moderate: 4-6:1 (standard cloud VMs)
Aggressive: 10-20:1 (burstable/preemptible)

Reason: Most VMs use <10% CPU average
- Web servers wait for requests
- Databases wait for queries
- Batch jobs run periodically
- Hypervisor schedules fairly when contention occurs
```

### Memory Overcommitment
```
Conservative: 1:1 (no overcommit)
Moderate: 1.2-1.5:1 (common)
Aggressive: 2:1+ (risky)

Techniques:
- Memory ballooning (reclaim unused RAM)
- Transparent page sharing (deduplicate identical pages)
- Memory compression (compress infrequently-used pages)

Risk: Memory can't "burst" like CPU
If overcommit fails → OOM kills (bad!)
```

### Storage Overcommitment (Thin Provisioning)
```
Physical: 100 TB SAN
Sold: 500 TB (5:1 overcommit)
Actually used: 80 TB

Works because: Customers don't fill their disks
Profit: Sell 5× more than you have
```

## Cloud Provider Tactics

### AWS
```
t3.medium (2 vCPU, 4 GB) - $30/month
- "Burstable" = Heavy overcommit (10-20:1)
- CPU credits system
- Highest margin instance type

m5.xlarge (4 vCPU, 16 GB) - $140/month
- "General Purpose" = Moderate overcommit (3-4:1)
- AWS sweet spot (volume + margin)

i3.metal (72 vCPU, 512 GB) - $4,992/month
- "Bare Metal" = NO overcommit
- You get entire physical server
- AWS makes less profit (but still 50%+ margin)
```

### Azure
```
B-series (Burstable) - Highest margin
- Baseline: 40% of CPU
- Can burst with "credits"
- Overcommit: 10:1 or more
- 85%+ margin for Azure

D-series (Standard) - Volume play
- Moderate overcommit (3-4:1)
- Most customers buy this
- 70-75% margin

Dedicated Host - Lowest margin
- No overcommit (you rent entire server)
- 20× more expensive than shared
- You're paying 1900% premium for NO sharing
```

### GCP
```
e2-medium (Shared-core) - $24/month
- Overcommit: 8-10:1
- Highest margin (85%+)

n1-standard-4 - $120/month
- Overcommit: 2.5-3:1
- Standard margin (75-80%)

Preemptible VMs - 80% cheaper
- Extreme overcommit (10-20:1)
- Can be killed anytime
- Pure profit from "spare" capacity
```

## The Noisy Neighbor Problem

Your VM performance depends on what OTHER VMs on your physical host are doing:
```
Physical Server:
├── Your VM: 10% CPU (idle, should be fast)
├── Neighbor 1: Bitcoin mining (100% CPU - violation!)
├── Neighbor 2: ML training (95% CPU)
├── Neighbor 3: Video encoding (90% CPU)
└── Result: Physical CPU maxed, YOUR VM slows down

You have ZERO visibility or control over this.
This is why cloud performance varies day-to-day.
```

## Your Competitive Advantage

### African Infrastructure Edge
```
1. Transparent Overcommit
   - AWS: Hidden, unpredictable
   - You: "We overcommit 4:1 CPU, 1.2:1 memory - here's why"
   - Customers appreciate honesty

2. Local Latency
   - AWS Africa: 200-400ms (routes to EU/US)
   - You: 5-20ms (local infrastructure)
   - 10-20× faster

3. Data Sovereignty
   - AWS: Data leaves continent
   - You: Data stays in Africa (compliance!)

4. Cost Structure
   - AWS margin: 70-80%
   - Your target: 40-50%
   - You can be 30-40% cheaper and still profit

5. Solar Power
   - AWS: Grid power ($0.10-0.15/kWh)
   - You: Solar ($0.02-0.05/kWh after amortization)
   - 50-75% power savings
```

### Your Pricing Strategy
```
AWS m5.xlarge: $140/month

Your equivalent:
├── Hardware cost: $15/month (amortized)
├── Power: $5/month (solar)
├── Network: $10/month
├── Operations: $20/month
├── Total cost: $50/month
├── Your price: $70/month (40% margin)
└── Customer saves: $70/month (50% vs AWS)

At 100 customers:
├── Revenue: $7,000/month
├── Costs: $5,000/month
├── Profit: $2,000/month
└── Customers happy (50% savings!)
```

## The Reality

AWS/Azure/GCP can't compete on price because:
- 70% margins baked into Wall Street expectations
- Lowering prices = stock price drops
- You: No shareholders, can operate on 40% margin
- Your pricing beats theirs every time

## Key Takeaway

Understanding overcommitment = Understanding cloud economics

You can build the same infrastructure, charge 50% less, and STILL make better margins per server.

That's the opportunity.
