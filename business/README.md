# Basics of GitHub

## prerequisites:

1. Make sure you have a github account, if you don't you can create one online at github.com


## Installation and SSH 
1. Download Git or GitBash if you're on Windows OS using the following link:
https://git-scm.com/downloads

2. Run GitBash as Admin
note: whenever you run a terminal, such as GitBash, do so in admin mode. 

3. Make a folder by typing in "mkdir yourfoldername"

4. Go into the folder by typing "cd yourfoldername"

5. Type the following command into your terminal to generate an SSH key:
\bf {ssh-keygen -t rsa -b 4096 -C "your_email@email.com"}

save this as 'key.ssh'

6. Keep clicking enter until your key is created. It is good practice to have a passphrase but it is not necessary right now.

7. To confirm that your key has been created and is in the right file go into the key.ssh type ls and you should type 'ls' and you should see it. 

8. in your terminal type:
\bf {cat key.ssh.pub}

and copy the result starting from ssh-rsa and ending with your email. DO NOT SHARE THIS CODE WITH ANYONE. 

9. Go online to your github account, click the circle on the top right with your profile picture and a menu should appear, go to 'settings'

10. In the bottom left, click on 'SSH and GPG keys' and then, under SSH keys, click on 'New SSH key'

11. Paste the result from your terminal and choose an appropriate name for your key, then click on 'Add SSH key'.

Now you can start using Github! 

Note: Keep your key safe, and ideally hide it somewhere other than your root folder! 


## How to Manage a Repository in GitHub: The Basics

1. Make a new repository by going to your Github online and clicking 'create new repository'. Select an appropriate name for your repo and keep it public for now. 

2. In your GitBash terminal, create a folder (or use the one from before) and in this folder type 

git innit

to innitialise your repository. You must do this for every folder. 


3. to 
