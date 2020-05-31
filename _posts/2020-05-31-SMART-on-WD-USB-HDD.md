---
layout: post
title: SMART on WD USB HDDs
---

I have a WD My Passport USB HDD, which me and my brother use for our backup
(rather than having one for each of us, we use a single HDD. Yes, we are
cheapskates). As it changes hands between the two of us fairly often, we
are naturally very concerned about its health.

I usually use smartmontools to retrieve the SMART data of my HDDs, but for
some reason, the default set of arguments won't do for the WD Passport.

    root@N148P:/home/aswin# smartctl -a /dev/sdb
    smartctl 6.6 2016-05-31 r4324 [x86_64-linux-4.9.0-3-amd64] (local build)
    Copyright (C) 2002-16, Bruce Allen, Christian Franke, www.smartmontools.org

    /dev/sdb: Unknown USB bridge [0x1058:0x259f (0x1014)]
    Please specify device type with the -d option.

    Use smartctl -h to get a usage summary

For the longest amount of time, I strongly believed I would have to use WD's
proprietary Windows application (yikes!) to monitor the disks. But then,
yesterday, I chanced upon this [page](https://www.smartmontools.org/wiki/Supported_USB-Devices).

It turns out using the "-d sat" argument would make smartmontools play nice
with my HDD!

    root@N148P:/home/aswin# smartctl -a -d sat /dev/sdb
    smartctl 6.6 2016-05-31 r4324 [x86_64-linux-4.9.0-3-amd64] (local build)
    Copyright (C) 2002-16, Bruce Allen, Christian Franke, www.smartmontools.org

    === START OF INFORMATION SECTION ===
    Model Family:     Western Digital Elements / My Passport (USB, AF)
    Device Model:     WDC WD10JMVW-11AJGS4
    Serial Number:    WD-WX71A76JAR7T
    LU WWN Device Id: 5 0014ee 6b18facb5
    Firmware Version: 01.01A01
    User Capacity:    1,000,171,332,096 bytes [1.00 TB]
    Sector Sizes:     512 bytes logical, 4096 bytes physical
    Rotation Rate:    5400 rpm
    Device is:        In smartctl database [for details use: -P show]
    ATA Version is:   ACS-2 (minor revision not indicated)
    SATA Version is:  SATA 3.0, 3.0 Gb/s (current: 3.0 Gb/s)
    Local Time is:    Sun May 31 19:26:13 2020 IST
    SMART support is: Available - device has SMART capability.
    SMART support is: Enabled

    === START OF READ SMART DATA SECTION ===
    SMART overall-health self-assessment test result: PASSED

The page has an extensive set of USB HDDs which the tool supports along with
special arguments, which might be needed to make them work with smartmontools.
In hindsight, smartmontools always tried to point me in the right direction,
asking to pass a value for the "-d" argument, but it is the page which really
helped me out.
