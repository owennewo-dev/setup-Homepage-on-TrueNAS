# setup-Homepage-on-TrueNAS

(just want a config template to get started? Copy my code from the `.yaml` files above and paste into your appropriate files!)

![192 168 4 45_30054_](https://github.com/user-attachments/assets/19e981f6-0514-48d2-b962-7c4909ea6de1)

Welcome to the only guide on the internet for installing and configuring Homepage on your TrueNAS Scale server!

(this is tested on TrueNAS Scale version 24.10)

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

I will share some simple steps on how to remote into your server to access the `yaml` configuration files

Open a terminal, I am using Windows PowerShell. Enter the command `ssh admin@your-server-IP` and then your TrueNAS password when promted.

![{196E4AD9-2D09-43C1-93E6-F60CE3ABB3DA}](https://github.com/user-attachments/assets/f0096723-13b9-45b1-a162-552d51a656a9)

Now run the command `sudo su` and your password again.

Go back to TrueNAS and copy the path of your `HP_Config` dataset by clicking the clipboard button

![Screenshot 2024-11-04 180123](https://github.com/user-attachments/assets/8f2cd256-e600-419c-a038-2a8b5ab7e58f)

Return to PowerShell, and enter `cd /mnt/(the path you just copied)` Example: `cd /mnt/Main/Homepage_Stuff/HP_Config`

You're in! Now you can type `ls` and if you see multiple `.yaml` files, you did it right!

Now you can edit any of those files by entering `nano (file you want to edit)` Example: `nano services.yaml`

Please refer to the official Homepage documentation to learn how to code your dashboard: https://gethomepage.dev/configs/ (click the menu options on the left side for the info)

Now, once you want to save your `.yaml` file and check your work, use the keystroke `ctrl + O (letter O)` and then `Enter` to save. If it gives you an error, you forgot to run the `sudo su` command earlier.

And if you want to exit `nano` do `ctrl + x`

If you want to see my configuration, I uploaded my files to this repo.
No need to download the files, just copy the code and paste it into your file. Make sure the file you paste the code in is the same name of what you copied from!

If this helped you, please give it a star. If you want to be notified when I update my config and the `.yaml` files, make sure to click watch!

Happy Homepage-ing!
