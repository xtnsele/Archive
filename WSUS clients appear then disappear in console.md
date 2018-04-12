**WSUS clients appear then disappear in console**

**Note:** When I login to each workstation and type in CLI (CMD)

    *wuauclt.exe /detectnow /reportnow*

I am able to see these machines from the WSUS console but the other would disappear.

**Reason for unexpected behavior** 

This happens sometimes to cloned servers because they are having the same SUSClientID.  

Each time the server contacts wsus, the entry in the WSUS console would get overwritten with the new server information and the existing machine would disappear.

**Solution**

Navigate to this registry path below and delete the "**SusClientID**" and "**SusClientIDValidation**" registry values in the key

    **HKLM\Software\Microsoft\Windows\CurrentVersion\WindowsUpdate**

And then restart the Automatic Updates service.

**Source**

https://social.technet.microsoft.com/Forums/lync/en-US/c331d314-2f04-4b07-a3fd-878183b8101d/wsus-clients-appear-then-disappear-in-console?forum=winserverwsus 

https://community.spiceworks.com/scripts/show/613-cloned-machines-not-reporting-into-wsus-server