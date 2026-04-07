# EDK2-CPU-undervolting-tool
EDK2-based Intel CPU undervolting tool, which can apply a voltage offset to the CPU without modifying the BIOS

Almost all notebook OEMs have Intel's Undervolt Protection (UVP) enabled by default at the factory, preventing users from adjusting the CPU voltage curve at the system level. While this strategy can improve system stability and reduce after-sales maintenance costs to some extent, it inevitably restricts performance tuning and power management for users with Intel HX55 processors.

Fortunately, most OEMs have not completely locked the voltage offset feature—UVP can theoretically be disabled. However, in certain specific models from some manufacturers, the UVP option cannot be properly turned off, rendering users unable to apply undervolt adjustments to the CPU within the operating system.

To address this, we created this project.

Interestingly, some Intel 13th/14th generation mobile processors (such as the i9-13900HX and i7-13650HX) use the same B0 stepping cores as desktop processors. This common design allows some desktop features to be ported to the laptop platform. 

Specifically, during BIOS operation, we can actively load desktop 0x104 or 0x105 version microcode. These early microcode functions are not fully developed, and Intel has not fully enabled the UVP mechanism, allowing users to freely offset the CPU voltage curve. On the desktop side, this method is often used to undervolt K-series CPUs on B-series motherboards and can bypass CEP (Current Excursion Protection), thereby achieving a greater amount of negative voltage. 

The above method is also effective on the laptop platform: after loading the old microcode, UVP is bypassed, and users can safely apply undervolting to reduce power consumption and temperature, and even improve multi-core performance. 

However, the CEP protection mechanism on the laptop platform itself cannot be disabled, so we cannot set as low ACLL (AC Load Line) values as on desktops, and the amount of undervolting is still somewhat limited. Nevertheless, compared to the situation where undervolting is completely impossible, this solution already provides considerable tuning potential for HX55 users.
