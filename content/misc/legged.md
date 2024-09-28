---
title: Proposal for legged rover design
description: RSL pitch
---

I will focus mostly on absorbing the impact. For the legged robot the locomotion is probably the easiest anyway. Just use high quality tires and we *should* be good.
## Pneumatic actuators
Cool links:
- https://ar5iv.labs.arxiv.org/html/2203.01595
- https://ar5iv.labs.arxiv.org/html/2108.01481
- https://arxiv.org/pdf/2011.06749v1A
- https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=976298

We arrive at some rather basic leg design as follows:
![Leg](/images/x1.png)
Unfortunately the impact aborption here is negligible, we do a quick calculation:


```python

d_stiff = 0.05 d_soft = 0.20
mass = 3, velocity = 20
K = 0.5 * mass * velocity**2

impact_force_stiff = K / distance_stiff
impact_force_soft = K / distance_soft
print(K/d_stiff, K/d_soft) # 12kN, 3kN
``````
(Im Vergleich, nen Schienbein haelt so ca. 4kN aus.)
![china](/images/chinese_magnecko.png)[^1]

There's a bunch of research on how to make these legs more
resistant, but the main issue is that it's not all that
useful. F.ex. if we can weight optimize for a 3m earth fall
that is very valueable, but few times will someone fall from
a multi story building.
![Fluid saving](/images/new_pneumatics.png)[^2]

Just to summarize. I think it's relatively improbable that the approach works.
Mainly, we can't stick the adequate pneumatics and resistance structures into the 3kg package.

Probably better to simply integrate good walking legs into a design that can actually fall the required distance



[^1]:[Patent Source](https://patents.google.com/patent/CN103991487A/en)
[^2]:[Paper Source](https://www.mdpi.com/2075-1702/11/2/236)
