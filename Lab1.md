# Lab Report
---

## First part: Install VScode

* Visit [the Visual Studio Code website](https://code.visualstudio.com/)
* Follow the instructions to download and install it on your computer.

![Image](Images/1.png)

* After downloading and installing, open Visual Studio Code

---

## Second part: Remotely Connecting

* In the terminal, enter the command `ssh cs15lwi23adm@ieng6.ucsd.edu`.
Noting that each person has a unique account letter following "cs15lwi23", which can be found in [your specific course account](https://sdacs.ucsd.edu/~icc/index.php)

![Image](Images/2.png)

* When you connect to the remote computer via the terminal, it will prompt you with the message `Are you want to continue connecting (yes/no/[fingerprint])?`. Simply type `yes` and press enter.
* You will then be prompted to enter your password. Try using the password associated with your tritonlink account first. If the password is incorrect, you will need to reset it on the course-specific website mentioned earlier. Please note that it may take a few minutes for the password reset to take effect.

![Image](Images/3.png)

* If you're unable to login to the remote computer, don't worry, some people may be able to login on the first try, some people may need to try a few times.
---
## Third part:
![Image](Images/resubmitVersion.png)

* Once logged into my account on the classroom computer, we can enter the following commands on both your personal computer and school computer:
- `cd ~` to navigate to the home directory
- `cd` to navigate to the previous directory
- `ls -lat` to list the files in the current directory, sorted by modification time
- `ls -a` to list all files, including hidden ones, in the current directory
- `ls <directory>` where <directory> is `/home/linux/ieng6/cs15lwi23/cs15lwi23abc`, where the `abc` is one of the other group members’ usernames
- `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/` to copy the file `hello.txt` to the home directory
- `cat /home/linux/ieng6/cs15lwi23/public/hello.txt` to view the contents of the file 'hello.txt'
*Entering `ls /home/linux/ieng6/cs15lwi23/cs15lwi23abc` in either the home computer or the remote computer terminal will not allow you to access to others’ accounts on the remote computer. 
*However, for the command `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`, the document `hello.txt` is only accessible on the remote computer. This is because the document is saved in the public directory of the remote computer. To access this document, you need to log into your account on the remote computer first.
---

## Fourth part: git, Github, and Github Pages

* First, ensure that you have a GitHub account associated with your UCSD email, and sign in. If you do not have a GitHub account, please follow the instructions on the website to sign up.

![Image](Images/7.png)

* Next, create a new repository and name it "CSE15L-Lab_Reports", and add a brief description about the purpose of the repository.

![Image](Images/8.png)

* Then, within the repository, create a new file by clicking the "add files" button. Give the file a name, such as "index.MD", and write something into the file.
* Click “Commit new file” to save the work. You should see a view of your repository that now lists a file called index.md, and you can then copy the link from your browser and share it with your friends. 

![Image](Images/9.png)

* After that, go to the repository's settings by clicking the "Settings" button at the top of the page. From there, navigate to the "Page" option on the left sidebar.

![Image](Images/10.png)

* In the settings, ensure that the branch is set to "main" and that all other settings are left as they are. Remember to save these changes.
You should then receive a message that the source has been added. After a short wait, a link will become available, which you can use to visit your website.

