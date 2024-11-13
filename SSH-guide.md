## Remote into Homepage Dataset on a TrueNAS Server

Open a terminal, I am using Windows PowerShell. Enter the command `ssh admin@your-server-IP` and then your TrueNAS password when promted.

![{196E4AD9-2D09-43C1-93E6-F60CE3ABB3DA}](https://github.com/user-attachments/assets/f0096723-13b9-45b1-a162-552d51a656a9)

Now run the command `sudo su` and your password again.

Go back to TrueNAS and copy the path of your `HP_Config` dataset by clicking the clipboard button.

![Screenshot 2024-11-04 180123](https://github.com/user-attachments/assets/8f2cd256-e600-419c-a038-2a8b5ab7e58f)

Return to PowerShell, and enter `cd /mnt/(the path you just copied)` Example: `cd /mnt/Main/Homepage_Stuff/HP_Config`.

You're in! Now you can type `ls` and if you see multiple `.yaml` files, you did it right!

Now you can edit any of those files by entering `nano (file you want to edit)` Example: `nano services.yaml`.

Please refer to the official Homepage documentation to learn how to code your dashboard: https://gethomepage.dev/configs/ (click the menu options on the left side for the info).

Now, once you want to save your `.yaml` file and check your work, use the keystroke `ctrl + O (letter O)` and then `Enter` to save. If it gives you an error, you forgot to run the `sudo su` command earlier.

And if you want to exit `nano` do `ctrl + x`.
