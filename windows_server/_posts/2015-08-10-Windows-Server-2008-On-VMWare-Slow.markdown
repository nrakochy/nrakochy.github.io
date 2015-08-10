Windows Server 2008 on VMWare is SLOW...
---
layout:     post
title:      Windows Server 2008 on VMWare is SLOW...
date:       2015-08-10 12:00:00
summary:    Some configurations to improve slow performance of Windows Server 2008 on VMWare. 
categories: VMWare 
---

Some configurations to improve slow performance of Windows Server 2008 on VMWare. 

VM settings (might seem excessive, but running the BMC platform):

    100 GB Hard Disk
    10 GB Memory

Configuring VM so that it does not hang on shutdown ([source](http://superuser.com/questions/424132/vmware-player-slows-down-computer-after-exit), [original, defunct source](http://bryonbrewer.com/?p=223)):

    path: \ProgramData\VMware\VMware Player\config.ini
    Add these lines:
    mainMem.useNamedFile = "FALSE"
    prefvmx.useRecommendedLockedMemSize = "TRUE"
    prefvmx.minVmMemPct = "100"

Update the driver to VMWare SVGA 3D driver ([source](https://communities.vmware.com/thread/264024),[documentation](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2004145)):

    To update the driver for the video card to use the WDDM driver:
    Right-click the desktop and click Screen resolution.
    Click Advanced Settings.
    Click Properties.
    Click the Driver tab.
    Click Update Driver.
    Click Browse my computer for driver software.
    Enter this location or click Browse and navigate to it:
        C:\Program Files\Common Files\VMware\Drivers\wddm_video
    Click Next. The driver is installed and you see a screen confirming that Windows has finished installing the driver for VMware SVGA 3D.
    When prompted, reboot the virtual machine to enable the new video driver.

Moved cache from Full to Quick Removal ([source](http://serverfault.com/a/508888))
