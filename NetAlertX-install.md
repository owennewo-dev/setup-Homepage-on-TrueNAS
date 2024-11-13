NetAlertX is a really cool network monitoring tool. The Homepage widget can notify you of any new devices that just joined your network or of important devices that have gone offline.

![{B17D286D-559B-4625-85BB-DAC17573AC31}](https://github.com/user-attachments/assets/ad7d7eba-2eec-4fdc-8f73-232732d84250)

Before we install NetAlertX you need to create some datasets for the data to be stored in.

Create one called `NetAlertX_Stuff`, and create three child datasets called `NX_Config`, `NX_DB`, and `NX_Log`.

![{7230D7B7-8C9C-4F0E-8B4A-4B7E5A4F2364}](https://github.com/user-attachments/assets/fe7031ea-ec7a-425b-855c-f58590eab994)

Select the `NetAlertX_Stuff` folder and edit the permissions. Under `Owner` select the `User` dropdown, search for and select `www-data`. Do the same for the `Group` dropdown. Check the boxes for `Apply User` `Apply group` `Apply permissions recursively` and `Apply permissions to child datasets`. On the right side of the menu check all the boxes.

![image](https://github.com/user-attachments/assets/2ecdd4aa-b6d8-4b5e-9d8b-9557c2c86019)

Now hit `Save`

Go to the `Apps`, click `Discover Apps`, then click the three dots menu next to the `Custom App` button, then click `Install via YAML`.

In the `Name` field enter `NetAlertX`.

Then paste the following code into the `Custom Config` box.
```yaml
version: "3"
services:
  netalertx:
    container_name: netalertx
    image: "jokobsk/netalertx:latest"      
    network_mode: "host"        
    restart: unless-stopped
    volumes:
      - /mnt/your-pool-name/NetAlertX/NX_Config:/app/config
      - /mnt/your-pool-name/NetAlertX/NX_DB:/app/db      
      - /mnt/your-pool-name/NetAlertX/NX_Log:/app/front/log
    environment:
      - TZ=Country/City      
      - PORT=20211
```
![{0F7BAD42-D529-4F2E-ABC9-DE94ADEC93A1}](https://github.com/user-attachments/assets/4ed13e01-f94e-49f7-8464-7b5ada7dd921)

Ensure you replace `/your-pool-name/` and `Country/City` with the correct information.

Now click `Save`

The app should deploy. Once it is running enter `http://your-server-ip:20211` into your browser.
