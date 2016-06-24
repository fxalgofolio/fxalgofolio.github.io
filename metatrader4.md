---
layout: page
title: FXAlgoFolio for MetaTrader 4
permalink: /metatrader4/
---

Download at [GitHub project page](https://github.com/fxalgofolio/fxalgofolio-mt4).

Based on the C-like language structure of MQL4, the framework is implemented for MetaTrader 4 as a library of boilerplate code included in the expert advisor code.

There are three "modes" implemented in this library:

* **Normal mode**: uses implemented system in normal trading execution.
* **Test mode**: uses system entries and exits in various selected tests.
* **Walk-forward mode**: uses the system within a restricted time range.

**_WARNING: Repeated testing with different test parameters contitutes optimisation. Studying the [primary reading material by Kevin Davey]({{ '/resources' | prepend: site.baseurl }}) is recommended prior to starting._**

Developed with this framework, a system is simply an implementation of three functions:

```cpp
bool SystemEntry();
```

Executes system entry strategy. This function only runs if there is no open order (pending orders are not open).

```cpp
bool SystemExit();
```

Executes system exit strategy. This function only runs if an order is open (including within the same bar as when the order is opened).

```cpp
void SystemSetExterns();
```

Updates system parameters. This can be used for walk-forward post-optimisation parameter modification based on date in order to produce a single backtesting equity curve.


Implementation
--------------

Deposit the `FXAlgoFolio` directory in the `MQL4/Includes` directory under the MetaTrader 4 data folder.

In a single Expert Advisor implementation, the general structure is as follows:

```cpp
#include <FXAlgoFolio/TestMode.mqh>

void SystemSetExterns()
{
   // Set walk-forward parameters for date range.
}

bool SystemEntry()
{
   // Run entry strategy.
   //...
   return true;
}

bool SystemExit()
{
   // Run exit strategy.
   //...
   return true;
}
```

A sample system is available in the project under the `examples` directory.

