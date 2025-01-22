# IT-212-KSA-1
set, show, clear passwords

(2960)
Release the Mode button when theSYSTLED blinks amber and then turns solid green. When you release the Mode button, theSYSTLED blinks green

>flash_init
>load_helper
>dir flash:
>boot

>rename flash:config.txt flash:config.old
>boot
# push n
>en
>rename flash:config.old flash:config.text
>
>copy flash:config.txt system:running-config
>
>enable secret <password>
>
#overwrite vty password
>line vty 015
>password <enter password>
#overwrite consol password
>line con 0
>password <new password>
>write momory

(2911)
#Either switch off or shut down the router.

#Remove the compact flash that is on the rear of the router. This image shows the rear of the 2951 router:

#Switch on the router.
#Once the router is on Rommon mode, reinsert the compact flash.
>show version
> confreg 0x2142
> reset
> no
> enable
> copy startup-config startup-config
> show running-config
>
> config terminal
> enable secret <password>
>no shutdown
>
> config-register <configuation_register 0x2102>
> end
> copy running-config startup-config


(1000)

# press mode and hold button for 60-90 seconds 
>flash_init
>load_helper
>dir_flash:
>rename flash:config.text flash:config.text.old
>boot

>copy flash:config.old running-config
>configure terminal
>enable secret Password123
>copy running-config startup-config

