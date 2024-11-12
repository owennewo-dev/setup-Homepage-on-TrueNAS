Glances is a system resources monitoring tool, and the Glances widgets in Homepage are really cool

![{8360EDDE-F813-4769-99BD-CBB8CD2771FB}](https://github.com/user-attachments/assets/aadfb655-5df6-4654-a176-fc08de32c33d)

Who doesn't want those on their homepage?!

To install Glances on a TrueNAS Scale server, go to the `Apps` menu and then click the `Discover Apps` button in the top right corner. Then click the `Custom Apps` button

In the `Application Name` field enter `glances`

In the `Repository` field enter `nicolargo/glances`

![{C9F76A9A-90CE-43B5-A8D9-114CA0B7E42A}](https://github.com/user-attachments/assets/d7b027f3-64f2-499f-bafa-125564777cb2)

Scroll down to `Container Configuration`

Enter your timezone

At `Environment Variables` click `Add`

A new box will appear. In the `Name` field enter `GLANCES_OPT`

In the `Value` field enter `-w`

![{1E260A0F-627B-4A1E-9C8E-9213B52EDFE3}](https://github.com/user-attachments/assets/a07f67c1-a6ef-489e-bd29-31a53b8fd858)

Scroll down to `Network Configuration`

Click the `Add` button next to `Ports` twice, fill out the fields the same as in the screenshot below

![{5A48E101-28EE-43F9-8201-1D3261CE236A}](https://github.com/user-attachments/assets/9cbe0acd-8a61-40e3-8bce-da8c57dfcaec)

You're finished! Scroll to the bottom of the page and click `Install`

Back in the `Apps` menu you will notice there is no `Web UI` button in the `Application Info` area. To access the UI enter the ip address of your server in your browser with `:61208` at the end

You should now see this screen

![{71E4837A-6205-46F7-AE28-501ACF9A94F5}](https://github.com/user-attachments/assets/b2557f91-2a94-4fee-aa1b-86a23c8fb474)

Now that Glances is installed properly, you can add the widgets to your Homepage. Refer to the [official documentation](https://gethomepage.dev/widgets/services/glances/) to learn how to configure the widgets

This is my code for the Glances widgets in my `services.yaml` file
```
- Glances:
    - CPU:
        widget:
          type: glances
          url: http://server-ip-address:61208
          metric: cpu
          version: 4
    - CPU Temp:
        widget:
          type: glances
          url: http://server-ip-address:61208
          metric: sensor:Package id 0
          version: 4
    - RAM:
        widget:
          type: glances
          url: http://server-ip-address:61208
          metric: memory
          version: 4
    - Network:
        widget:
          type: glances
          url: http://server-ip-address:61208
          metric: network:eth0
          version: 4
    - Boot Drive:
        widget:
          type: glances
          url: http://server-ip-address:61208
          metric: disk:sdb
          version: 4
    - Mirrored Drive 1:
        widget:
          type: glances
          url: http://server-ip-address:61208
          metric: disk:sdc
          version: 4
    - Mirrored Drive 2:
        widget:
          type: glances
          url: http://server-ip-address:61208
          metric: disk:sda
          version: 4
