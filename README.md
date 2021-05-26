# Linking Visual Studio Code to Github repository
###### Author: Muhd Arif Rawi
###### Date published: 25 May 2021

## Introduction
This guide is meant for new users of Github and Visual Studio Code (VSC). This guide assumes that the user 
has already made an account for Github, installed Git and have VSC installed in their computer. 

> **NOTE: This guide assumes that the user is currently using Windows 10 OS**

If they have not done so, they can visit the following sites:
- [Visual Studio Code](https://code.visualstudio.com/download)
- [Github](https://github.com/join?source=login)
- [Git-scm](https://git-scm.com/downloads)

> **IMPORTANT: Installation should be made into your main drive where the system programs are. You can choose to 
> install it in another drive but you may have difficulties trying to setup Bash as your in-app terminal.**

## Content
- Main contents:
    - [Creating new project folder and opening in VSC](#)
    - [Creating a new repository in Github](#)
    - [Initialising Git in your computer](#)
        - [Checking the terminal directory](#)
        - [Step-by-step initialisation with explanation](#)
    - ["Please tell me who you are" error](#)
    - [Pushing to your repository throughout your project timeline](#)
- Additional contents:
    - [Multi-line commits](#)
        - [Using line breaks](#)
        - [Using vim](#)
    - [Cloning and pushing (personal) repositories](#)
    - [Branching](#)

## Creating new project folder and opening in VSC
There are a few ways you can create a project folder and open up VSC. The simplest for a beginner however, is to simply create 
a project folder ahead of time. 

1. Find the destination where you wish to create your project folder. 
2. Create a new **folder**. Name the folder with you project name. The norm would be to key in the date you started your project 
    followed by your project name. Example: `25May2021-vsc-github-guide`. 

> **NOTE: Notice that there are no space in-between the words. Instead, dashes are being used to replace them. Subtituting 
> spaces with either dashes or underscores is a common practice in programming as it reduces any chance of potential errors.**

4. Find the VSC program and open it.
5. Open project folder by clicking on the blue "Open Folder" button or press "File > Open Folder...".

![screenshot of VSC new window](\images\vsc-screenshot-1.jpg)

## Creating a new repository in Github
Once you have created and logged in to your Github account, you will be greeted with the dashboard.

![image of github dashboard](\images\github-screenshot-1.jpg)

You can click on the green button labelled "new" on the left of the page to create a new repository. Alternatively, you can 
click on your profile icon on the top-right of the page, select "Your repositories" on the dropdown and press the same 
green button. 

After clicking on it, you would be directed to the "Create a new repository" page. 

![image of github create a new repository page](\images\github-screenshot-2.jpg)

Do the following:
1. Ensure that the "Owner" section has your Github account name.
2. Key in a unique name in the "Repository name" section. Again, the norm would be to key in the date you started your project 
    followed by your project name. Example: `25May2021-vsc-github-guide`. Additionally you could put in the time as well. 
    Example: `25May2021-2200-vsc-github-guide`.
3. Leave the radio button selected to "Public".
4. Leave the three checkboxes (add readme, add gitignore and choose license) unchecked.
5. When you are sure of everything, click on the green "Create repository" button.

Github would create a repository and lead you to the webpage. **Keep this page opened**.

![image of github repository page before linking](\images\github-screenshot-3.jpg)

## Initialising Git in your computer

On the repository webpage, focus only on the first section which says "…or create a new repository on the command line".

From here, you can copy and paste, line by line into the in-app terminal.

You can access the in-app terminal by clicking on "Terminal > New Terminal". 

The terminal of your choice does not matter. Most users would prefer to use Bash as their terminal but for demonstration, this guide would be using `cmd`.

![image of vsc with CMD loaded into the in-app terminal](\images\vsc-screenshot-2.jpg)

> **IMPORTANT: Ensure that your terminal directory is directed into your project folder.**

### Checking the terminal directory
There are a few ways to check but this would be the easiest way to do:
1. Key in `dir` into your terminal. If you are in a new empty project folder, there should be no files in them. If you find that you are not in your project folder, look at step 2.
![image of VSC terminal with DIR command entered](\images\vsc-screenshot-4.jpg)

2. If you keyed in `dir` and see your project folder, chances are, your terminal directory is incorrect. Key in `cd` followed by your project folder name. 
![image of VSC terminal with CD and DIR commands entered](\images\vsc-screenshot-5.jpg)


### Step-by-step initialisation with explanation
Once you are sure that you are in the correct directory, copy and paste the codes from the new repository page. These steps would only need to be done when you **first intialise git for a new project**.

> **IMPORTANT: Edit out the `< >` in the code. Those are unique fields dependant on project repository.**

> **NOTE: If the code you entered does not show any text or notification, it means that the code you entered has run successfully. Sometimes it would return some notification. 
> Read through it, as long as it does not say `ERROR` or `FATAL`, you are good to go.**

1. Create README.md with the project title:
    ```
    echo "<this is your project name>" >> README.md
    ```

    This code would create a README.md file with your project title. You can leave this step out **If you already have some files created in your project".

2. Add README.md:
    ```
    git add README.md
    ```

    This code would add README.md into the staging area. No other files would be added. 

    Alternatively, you can use the following code if you wish to add all files into the staging area:
    ```
    git add .
    ```
    > **NOTE: Note that there is a space between the `add` and `.` .**

    > **IMPORTANT: `git add.` will add ALL your files it can find in your project folder. If you want git to ignore certain files, you can create a `.gitignore` file. 
    > FreeCodeCamp has a summary of how you could do so: [gitignore explained](https://www.freecodecamp.org/news/gitignore-what-is-it-and-how-to-add-to-repo/).**

3. Commit the staged file:
    ```
    git commit -m "first commit"
    ```

    This would label or give a short title to the files you staged. 

    At this point, if this is your first time committing, you would encounter the `please tell me who you are...` error. Just follow the instruction and run this step again. 
    If you are unsure, you can look at ["please tell me who you are.. "]() section on how to configure.

4. Renaming Master to Main:
    ```
    git branch -M main
    ```

    This changes your current branch name from Master to Main. 
    > **NOTE: Note that the letter 'm' is capitalised.**

5. Adding origin:
    ```
    git remote add origin <your repository HTML path here>
    ```

    This gives the address for your computer to send your codes to whenever you push to Github.

6. Pushing your code to Github:
    ```
    git push -u origin main
    ```

    This will push your codes to the origin you have specified.

> **NOTE: Github may pop-up on another window to ask permission and authenticate. Go ahead and allow Github to do so.**

## "Please tell me who you are..." error
##### Source Reference : [Git: “please tell me who you are” error](https://stackoverflow.com/questions/11656761/git-please-tell-me-who-you-are-error)


After entering `git commit -m ...`, you may encounter the above mentioned error. This would only happen if you are committing your codes for the first time (or accidentally removed the config).

To remedy this, simply follow the instructions. 

> **NOTE: You can choose to give a fake email or nickname to the system. There has been no major issues found by doing so.**

1. Let the system know of your name:
    ```
    git config --global user.name "<your name here>"
    ```

2. Let the system know of your email:
    ```
    git config --global user.email "<your email here>"
    ```

3. If you were committing a code, run the commit code again. 



## Pushing to your repository throughout your project timeline
You would mainly require three codes after intialising Git in your project folder. It is advisable to frequently commit and push your codes whenever you reach a significant checkpoint in your code.

1. Add **ALL** codes to staging area:
    ```
    git add .
    ```
2. Commit staged code:
    ```
    git commit -m "<your commit message here>"
    ```
3. Push code:
    ```
    git push
    ```

Alternatively, you would want to look at creating [multi-line commits]() to give more context to your commits.

## Multi-line commits
To better describe or give a breakdown of the changes you may have made, you may want to use a multi-line commit. You should still give a short, precise and descriptive commit message
and not a lengthy essay. Remember, those reading your changes would not have the time to read a lengthy essay.


### Multi-line using line breaks
You can do line breaks in `git commit -m "..."`. You can read more in from here: [Add line break to 'git commit -m' from the command line](https://stackoverflow.com/questions/5064563/add-line-break-to-git-commit-m-from-the-command-line)


### Multi-line using vim
Another way to do a multi-line commit, instead of typing `git commit -m "..."`, simply type in `git commit`.

This would either open a new file tab/window or open up `vim` in your terminal.

#### If it opens a new file tab/window
Simply type in your commit message, save the file (just like how you would save any file) and close the window. 

The terminal will continue to run the commit once the commit tab/window is closed. 

#### If it opens vim in your terminal
To start inserting text, press on the `i` key, navigate down to the bottom and start typing.

Once you are done, press the `esc` key on your keyboard and type in `:wq`. This will save and exit the file. The terminal will continue the commit once you save and exit from `vim`.

You can read more about `vim` here: [How do I save changes in vim](https://www.cyberciti.biz/faq/how-do-i-save-changes-in-vim/)

## Cloning and pushing (personal) repositories
Run the following code to clone your repository:
```
git clone <your repo directory here>
```

At this point, you will have an error if you try any `git commit` procedures. You will have to find 
that folder it created to clone and change directory (`cd <folder name>`) into it. 


## Branching
##### Source reference: [Check, create or edit branches](https://git-scm.com/docs/git-branch)

### Creating a branch:
```
git branch <branch name here>
```

### Changing branch:
```
git checkout <branch that you want to move to>
```

### Merging from dev branch to main branch:
##### Source reference: [Merge development branch with master](https://stackoverflow.com/questions/14168677/merge-development-branch-with-master)
```
<#on branch development>
git merge master <#resolve any merge conflicts if there are any> 
git checkout main 
git merge development <#there won't be any conflicts now>
```

## Additional helpful git commands
### Check on the current status 
##### Source reference: [git-scm git status](https://git-scm.com/docs/git-status)
```
git status
``` 
### See what will be committed 
##### Source reference: [git-scm git ls-files](https://git-scm.com/docs/git-ls-files )
```
git ls-files <add any optional commands here>
```
### Checking remote branch 
##### Source reference: [git-scm git remote](https://git-scm.com/docs/git-remote)
```
git remote <add any optional commands here>
```
### Checking where you remote is 
```
git remote -v
```

## Afterword
### License and usage
License: Public Domain and Open Source.
Usage: Feel free to fork, download or copy my guide. Do attribute it back to me. 

### Disclaimer
I do not claim ownership of any software or codes found in this guide. They belong to their respective creators. I have done my best to attribute it back to them.
Additionally I do not claim to be a master in this field. I wrote what I understood to the best of my ability. 

### Support this guide
Give it a star? I don't know what it does though lol.
