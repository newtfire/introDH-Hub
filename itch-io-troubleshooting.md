## Troubleshooting installation issues for itch.io games

When we have trouble starting an itch.io game after downloading it, here are things we've tried that have succeeded in getting it to work.
Most issues are to do with your operating system not recognizing or trusting an indie supplier of software, and we need to check file permissions and override some security settings.

### Mac 

On Mac, move the Game you downloaded to your Desktop or somewhere outside your Downloads directory.

Open your Terminal (the same one you use for GitHub) to the location of the game. (You can right-click on the game, choose "Services", and choose to open the location at your terminal. The Game app is actually a folder with files inside.
 
* In your terminal, run `ls` and look for a folder named "MacOS" or something that looks like it might contain files specific to running the game on Mac. Use `cd` to navigate into that folder, and use `ls` to look inside. For the game "Where the Goats Are," for example, I found a file inside MacOS/ named "WheretheGoatsAre1.0.2fMac" 
* From the terminal "standing on" the folder containing the Mac file you just found, run `ls - lisa` to see the file permissions on the file. When I ran this, I saw `rw-rw-r--`. Those are file permission settings, and the series should be `rwxrwxr-x`. We can change it with this command:
```
chmod 775 Where[tab]
```
Here I started typing the first few letters and hit the tab key to autocomplete the filename. When you run this, you can check the permissions again with `ls - lisa` and see that they are changed. 

Now, if you try opening the file, you'll see a different error: Mac won't want to open something from an unidentified developer. Bypass that with:
[control] + click
Then you see a different screen: Are you sure you want to open something from an unidentified developer? Answer: yes. 


### Windows
