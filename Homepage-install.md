Create a dataset for the configuration files to go in named `Homepage_Stuff` and a subfolder named `HP_Config`

![{66E4D9EC-C9AB-4E2A-859A-7C6697954306}](https://github.com/user-attachments/assets/fae3b763-23f4-4007-9def-d112c71a6a8b)

Select the `Homepage_Stuff` folder and edit the permissions. Under `Owner` select the `User` dropdown, search for and select `www-data`. Do the same for the `Group` dropdown. Check the boxes for `Apply User` `Apply group` and `Apply permissions recursively`. On the right side of the menu check all the boxes.

![{673E02C2-88EE-4E0C-8EFD-5EAC3C323F32}](https://github.com/user-attachments/assets/e1c5e0e7-86c9-4ae0-9622-5f67ad2abe51)

All done, now hit Save

In the Discover Apps menu, search for Homepage. Click it and then click `Install`.
   
Leave everything default, except for `Storage Configuration`. In the `Type` dropdown select `Host Path`

A new dropdown called `Host Path` will appear. Click it and find the `HP_Config` dataset, click it.

![{F32FAA0E-562A-49CB-B74C-0D90EF549799}](https://github.com/user-attachments/assets/d6681307-adab-4e4b-98db-3f3b146d9732)

Scroll down and click `Install`

You should now see Homepage in your app list

![{DB3F1B59-4194-4D00-AD24-8682EF55EE5D}](https://github.com/user-attachments/assets/ad0545a1-bf81-40c1-8095-43ce9b9894db)

Click the Web UI button, now your ready to create your dashboard!

Now head over to [How to remote into your server to configure the `.yaml` files](https://github.com/owennewo-photo/setup-Homepage-on-TrueNAS/blob/main/SSH-guide.md)
