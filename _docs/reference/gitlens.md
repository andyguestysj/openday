---
title: GitLens
permalink: /docs/gitlens/
---

## GitLens

If you've installed the GitLens extension correctly there should be an icon in the bar that looks like this.  

<centre>        
    <img src="{{ "/assets/img/ext-git.png" | relative_url }}" alt="VSC Button Bar - Source Control" class="img-responsive">
</centre>

Click on the button to open the Source Control sidebar.  

<centre>        
    <img src="{{ "/assets/img/git-clone1.png" | relative_url }}" alt="VSC Button Bar - Source Control Bar" class="img-responsive">
</centre>

Click on the **Clone Repository** button and enter the URL https://git.ysjcs.net:8888/a.guest/javahelloworld.git in the window that pops up.  

Create a new folder to clone the repository to and select it.  

<centre>        
    <img src="{{ "/assets/img/git-clone2.png" | relative_url }}" alt="VSC Clone Repo" class="img-responsive">
</centre>

Click the **Open** button.

<centre>        
    <img src="{{ "/assets/img/git-clone3.png" | relative_url }}" alt="VSC Clone Repo" class="img-responsive">
</centre>

You should now have a copy of the *Hello World* Java program.  

If you have installed the Code Runner extension properly you should be able to compile and execute the code by pressing the play button in the top right od the Visual Studio Code window (it looks like a little triangle).  

### Manually Compiling and Executing Code

To manually compile the code, first select the Terminal window at the bottom of VSCode. (If it isn't there, you can open it from the View menu or by pressing Ctrl + ').

First you need to compile the code. The code is in the `src` folder and we want to put the executable in the `bin` folder. We do this by typing in :-

```console
javac src\App.java -d bin
```

Then, if the code has compiled witout errors, to execute the file we enter :-

```
java -cp bin App
```

This tells java to look for App in the bin folder.  


