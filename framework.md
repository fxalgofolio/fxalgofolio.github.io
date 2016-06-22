---
layout: page
title: Framework
permalink: /framework/
---

The framework is built on the principle of maximizing the probability (where practical for individual traders) that a trading system performs well, whatever your individual goals.

This framework assumes a trading system is designed for a specific timeframe (i.e. time interval for each bar, e.g. 1-hour) and is comprised of:

* Entry criteria, which contain entry signals and entry mechanism (e.g. type of order, price gap).
* Exit criteria, which control how an open trade is closed (e.g. stop-loss orders, exit signals).
* Entry/exit parameters, which provide a tunable range of system behaviors.

Based on the measurement of good system performance, each failed test attempting to demonstrate the performance as a fluke raises the confidence in the system being actually good. **ANY** optimization, however subtle, increases the risk of overfitting your projected system performance to historical data. Thus a trading system with statistically significant good performance must follow these criteria:

* Testing data must be different from optimization data (out-of-sample testing).
* The system employs simple rules with few parameters, which generalizes better out of sample.
* The system is optimized and tested across multiple periods (walk-forward testing) and is thus less likely to stop working immediately going forward.
* The system is not over-tested on too many different combinations of circumstances (e.g. different instruments, different time frames, different walk-forward periods).

Once this risk is controlled via specific prudent practices in the system development process, statistical techniques are applied in order to attempt to further ensure the high probability of entries and exits:

* System entry, random exit
* System entry, fixed-bar exit
* System entry, fixed-level exit
* Random entry, system exit
* Trend-following entry, system exit
* Counter-trend entry, system exit

The complete testing framework is implemented to target [a specific platform]({{ '/#platform' | prepend: site.baseurl }}) for the usage of historical data in testing. Testing methodology is documented in the [primary resource]({{ '/resources' | prepend: site.baseurl }}).

