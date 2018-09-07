Burst speed concept
===================

Burst is a technology that is part of Splynx bandwidth manager. It's supported by Mikrotik RouterOS devices. Splynx can create speed limits with burst option via Radius protocol or via API.

Burst concept is about to allow customer transfer data with higher speed that is in his tariff plan but for some period of time.Burst will work in case ehn **average-rate** of the queue for the last **burst-time** seconds is smaller that **burst-threshold** value. Burst stops when **average-rate** of the queue for the last **burst-time** seconds is higher or equal to **burst-threshold** value.

When burst is applied **burst-limit** value replaces the **max-limit** value inside the queue.

Description of the burst terminology and Splynx usage:

**burst-limit** (set in %) : it is a maximal upload/download speed which client can get when the burst is allowed. We set it up in % of the speed of the plan. If customer has a plan of 2 Mbps with burst-limit 100%, he will get bust speed of 4 Mbps. If we setup burst-limit in Splynx to 50%, then customer will get under burst 3 Mbps instead of original 2 Mbps of the plan.

**burst-time** (seconds) : period of time when average data rate is calculated. It's not the time when burst is active.

**burst-threshold** (set in %) : Bust technology always compares average speed with threshold. When average reaches threshold, burst is disabled. We also define it in % in Splynx. For example if we set up 80% of threshold of 2 Mbps plan, the threshold value will be set to 1.6 Mbps and bust will be deactivated when average speed during burst-time will reach 1.6 Mbps.

**average-rate** (not setup in Splynx, default value) : Every 1/16 part of the **burst-time**, Mikrotik router calculates the average data rate over the last **burst-time** seconds

**actual-rate** (read-only value) : actual traffic transfer rate of the queue, it's used in the picture below for better understanding of concept. On picture is an example of plan with bust-time 16 seconds, tariff speed of 2 Mbps and burst-rate of 4 Mbps, threshold is set to 1.6 Mbps.

![Burst_mikrotik1.JPG](Burst_mikrotik1.JPG)![Burst_mikrotik.JPG](Burst_mikrotik.JPG)

To setup the burst which will provide service as on the picture we have to configure Splynx tarrif plan this way:

![Burst_splynx.png](Burst_splynx.png)

We recommend to use burst time of 30 or 60 seconds, and value of threshold around 70-80% of the plan.