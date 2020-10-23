# Getting Started with GitHub

## Pre-requisites:

1. Make sure you have a github account, if you don't you can create one online at github.com . 


## Installation and SSH 
1. [Download GitBash](https://git-scm.com/downloads) if you are using Windows OS using the following link

2. Run GitBash as Admininistrator by right clicking the application and clicking the 'Run as Administrator' option. 

**Note**: Whenever you run a terminal, such as GitBash, do so in admin mode. 

3. Make a folder by typing in 

```mkdir yourfoldername```

4. Go into the folder by typing

```cd yourfoldername```

5. Type the following command into your terminal to generate an SSH key:

```ssh-keygen -t rsa -b 4096 -C "your_email@email.com"```

when prompted, save this as **key.ssh**

6. Keep clicking **enter** until your key is created (should be 3 times). It is good practice to have a passphrase but this is not necessary to get started.

If you would like to create a passphrase, you can do so when promted and then click **enter**. 

7. To confirm that your key has been created and is in the right file go into the key.ssh directory by typing

``` cd key.ssh ```

type 

```ls ```

This should reveal a list of files in the directory, which should include **key.ssh.pub** which is your public SSH key. 

8. To copy your public key, in your terminal type:
```cat key.ssh.pub```

and copy the result starting from **ssh-rsa** and ending with your email. 

__DO NOT SHARE THIS CODE WITH ANYONE.__

9. Go online to your github account, click the circle on the top right with your profile picture and a menu should appear. Click on *settings*.

10. In the bottom left, click on *SSH and GPG keys* and then, under SSH keys, click on *New SSH key*

11. Paste the result from your terminal and choose an appropriate name for your key, then click on *Add SSH key*. 

__Now you can start using Github!__

**Note:** Keep your key safe, and ideally hide it somewhere other than your root folder. 


## Creating and Committing to a Respository in GitHub

1. Make a new repository by going to your Github online and clicking *create new repository*. Select an appropriate name for your repo and keep it public for now. 

2. In your GitBash terminal, create a directory with the same name as your repository:

``` mkdir name_of_repository ```

3. Go into the folder

``` cd name_of_repository ```

and nitialise the folder as a repository using the command:

```git init``

** You must do this every time you create a new repository **


4. Create a Markdown file, we'll call it 'README' for now:

``` touch README.md ```

the ``` .md ``` specifies that this is a Markfown file. 

5. Start editing your Markdown file using the command: 

``` nano README.md ```

This will open a Markdown editor called nano, there are other editors you can use, such as vi or Visual Studio. 

6. Type something into your file, perhaps a title: 

``` # This is my file ```

7. Save and Exit the file using *CTRL X* then *Y* when prompted then *Enter*

This step will vary depending on what editor you are using. 

8. Type the following command: 

``` git remote add origin git@github.com:USER_NAME/Repo_name.git ```

Every time you want to push a folder for the first time, you need to use this command. 

9. To upload your file to GitHub, carry out these three commands. You need to repeat these every time you want to upload to GitHub. 

``` 
git add . (or git add filename.filetype)

git commit -m "logical description of your change"

git push -u origin main
    OR 
git push -u origin master 
```

Whether you use ``` main ``` or ```master``` depends on what the blue brackets after your current location say. 
