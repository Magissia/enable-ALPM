# Enable Aggressive Link Power Management

Aggressive Link Power Management (ALPM) is a mechanism where a SATA AHCI controller can put the SATA link that connects to the disk into a very low power mode during periods of zero I/O activity and into an active power state when work needs to be done. Tests show that this can save around 0.5-2 Watts of power on a typical system. 

ALPM is now available in several SATA controllers that use the Advanced Host Controller Interface (AHCI). However, there is evidence that some controllers may go into a low power state incorrectly and this ends up causing data loss. Since there is a chance that this can cause data loss do not enable it unless you have backups of your data and are willing to take the risk.

This package does nothing fancy and you can do the same from terminal using echo SATA_ALPM_ENABLE=true | sudo tee /etc/pm/config.d/sata_alpm, but some people prefer to not use the terminal and this is for them.
