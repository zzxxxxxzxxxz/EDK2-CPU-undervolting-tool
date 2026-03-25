# EDK2-CPU-undervolting-tool
EDK2-based Intel CPU undervolting tool, which can apply a voltage offset to the CPU without modifying the BIOS

Almost all notebook OEMs have Intel's Undervolt Protection (UVP) enabled by default at the factory, preventing users from adjusting the CPU voltage curve at the system level. While this strategy can improve system stability and reduce after-sales maintenance costs to some extent, it inevitably restricts performance tuning and power management for users with Intel HX55 processors.

Fortunately, most OEMs have not completely locked the voltage offset feature—UVP can theoretically be disabled. However, in certain specific models from some manufacturers, the UVP option cannot be properly turned off, rendering users unable to apply undervolt adjustments to the CPU within the operating system.

To address this, we created this project.
