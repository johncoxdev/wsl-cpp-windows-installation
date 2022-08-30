# WSL & G++ (C++ compiler) installation -- Using Visual Studio Code

This was made in order to help students with the installation oF WSL, g++, and the work arounds using Visual Studio Code from Rincon's 2022 Fundamentals of Operating Systems class.

```diff
- Troubleshooting is at the end for simple issues that may arrise!
```

## Instructions/Guide:

1) Open Powershell/CMD with admin perms.
2) Download WSl with `wsl --install`. This will require a system reboot.
3) Open your windows tart menu and type , `Ubuntu`, if nothing pops up, then you're going to have to download it from the Window's Store.
4) Once your Window's store is open, type "Ubuntu" with the search tab and download the app from it.
5) This will download and then depending on your computer, its either going to autocomplete it or you're going to create a profile. It's fairly simple, set your username and password to your liking and just continue basically.
6) Once finished, the Ubuntu terminal should now open, if not, just go to your start menu and type `Ubuntu` and run the app.
7) First thing, do the follwing command `sudo apt update && sudo apt upgrade` within your Ubuntu terminal. Just type `y` if the terminal is asking to reserve/use space within your disk.
8) Once it's done downloading, run the following command `sudo apt-get install build-essential gdb`. Type `y` if it ask you to. *(This is your C++ Compiler being installed.)*
9) Once it's done downloading, run the following command `mkdir RinconOperatingSystems` (This is going to create a folder in the root of your WSL. This is essentially where your homework and such is going to be stored.)
10) Go within that folder you just created by doing the command `cd RinconOperatingSystems/`
11) Run the command `code .` *(This is going to more likely download and/or open Visual Studio Code within your WSL)*
12) First thing, download the necessary extentions. Go to the extentions tab found on the left side of your screen *(looks like four boxes)* and download the following items.
  - C/C++ *By: Microsoft*
  - C/C++ Extension Pack *By: Microsoft*
  - Remote - WSL *By: Microsoft*  
**This will require a VSCode restart**
13) Create a basic `main.cpp` file that prints Hello World to console.
14) On the left side of the screen, click on area that looks like a play button. Click on `Create a launch.json` on the left panel area. This should automatically create a basic launch.json within the folder called, `.vscode`.
15) Go to the folder that Rincon provided in Blackboard for `VS Code File - WIN - WSL`
16) Once extracted, then you're going to want to grab three files *(keybinding, task, & launch)* from the `WinFiles`, and drag and drop them within your `.vscode` folder that was automatically created when you did step 14. Replace all of the files.
17) You can try doing `CTRL + r`, to see if your keybindings are working. If not, you can also do f5 or going to the play button again, and clicking on the green play button you see near the top left of your screen.
18) You should then see a bunch of debugging ouput within your `Debug Console` tab and also see an output of 'Hello World' in your `Terminal` tab. If you see these, you are now complete!


## Troubleshooting

> "**How do I go back to my WSL workplace once I closed it?**"
- *There is three main ways you can go about this.*
  1) Open VSCode and see if VSCode will restore your previous workplace.
  2) Open VSCode and click on `file` on the top left, click `Open Recent` and find it through there. You're probably looking something as `~/OperatingSystems/ [WSL: Ubuntu]`.
  3) Close your Ubuntu terminal, reopen it, and follow steps 10 & 11.

> "**My key bindings that Rincon provided isn't working!**"
- *The way I fixed this was by setting the global keybinds, since VSCode does not provide workplace specific custom keybinds.*
  1) Open VSCode WSL workplace and click `CTRL+SHIFT+p`, type `Open Keyboard Shortcuts`, and click on `Preferences: Open Keyboard Shortcuts (JSON)`. This is going to open a `keybindings.json` file.
  2) Go back to the `keybindings.json` that Rincon provided and copy & paste it within the `keybindings.json` file that VSCode opened. Make sure there is no errors, you are rewritting the entire file.
  3) Save it and close the files. Click `CTRL+r` and it should be working normal now.

> "**My main.cpp ins't running!**"
- *Your main possible issue is that you created a main.cpp file within your `.vscode` folder. Just drag it outside that folder and attempt to run it again. This should fix that issue.*

> "**I can't drag and drop the files from Rincon**"
- *Make sure that you have extracted the file from the zipped folder. Its going to create a new folder and/or simply open a new window. Either open the new folder or use the new window- This will now allow you to drag and drop the files from the unzipped folder.*

> "**Which files am I moving to VSCode from Rincon's?**"
- *The WinFiles. The path shoould kind of look like...*  
  |- WinFiles   
  |---\_MACOSX  
  |------*(Files we dont need)*  
  |---WinFiles  
  |------.DS_Store           
  |------keybindings.json    
  |------launch.json    
  |------tasks.json  
  *Within the WinFiles>WinFiles>..., You're going to then drag and drop teh keybindings.json, launch.json, and task.json*  

> "**I am stuck on step 14, clicking on the play button will not tell me to create a launch.json**"
- *That's fine, what you're going to do is create a folder. It should by the symbol right next to the create file. You're going to name the folder `.vscode`. You may now continue to the following steps.*

> "**The command I'm doing is not working inside the terminal!**
- *A common error is a user error, which typically is a simple typo. Make sure you are typing the commands correctly!*"

> "**What do I do with the files Rincon provided?**"
- *Please follow steps, 15-18. If you're continuing to have trouble, please look at #4, #5, #6, and #7 in troubleshooting.*

> "**VSCode didn't make a .vscode folder, what do I do?**"
- *Follow Troubleshooting #6*
