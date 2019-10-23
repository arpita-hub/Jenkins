
# Learning by Doing | Jenkins Setup

## Introduction
In this section we will learn how to work with freestyle jenkins jobs.

## References
* https://www.tutorialspoint.com/jenkins/index.htm

## Assignments
### Must Do
* Create a freestyle job to print "Hello world".
```
Click On new item
Enter the name 
Select the Freestyle Project
Click ok 
Open the Job
Click on Configure
Go to Build Section
Click on Add Build Step
Select Execute Shell
Write : echo "Hello World"
Click on Apply and Save
![image](folder/image.png)
```

* Create a freestyle job to which take absolute path of a directory then
```
 * List all files and directories inside that.

Click On new item
Enter the name 
Select the Freestyle Project
Click ok 
Open the Job
Click on Configure
Go to Build Section
Click on Add Build Step
Select Execute Shell
Write : cd /home/arpita/Documents/
	ls
Click on Apply and Save
![image](jenkinsImg/image.png)
```

```
   * Print a message "drectory not exist" if directory doesn't exist on file system
Click On new item
Enter the name 
Select the Freestyle Project
Click ok 
Open the Job
Click on Configure
Go to General Section:
	Check : This Project is Parameterized
	Select String Parameter
	Enter Name, Default Value, Description

Go to Build Section
Click on Add Build Step
Select Execute Shell
	Write : cd /home/arpita/Documents/
		if [ -d "$dir" ]
		then 
		echo "Directory exists"
		else
		echo "Directory not exists"
		fi
Click on Apply and Save
![image](folder/image.png)
```

* Print "Inappropriate permissions" if you don't have permissions to list files.

```
Click On new item
Enter the name 
Select the Freestyle Project
Click ok 
Open the Job
Click on Configure
Go to Build Section
Click on Add Build Step
Select Execute Shell
Write : cd ~/secrets/
	if [ $? eq 0 ]
	then
	ls
	else
	echo "Inappropriate Permission "
	fi
Click on Apply and Save
![image](folder/image.png)
```

* Update the previously created freestyle job to only retain last 10 build history but not beyond 2 days.

```
Install Discard Old Build Plugin
This plugin enables detail configuration to discard old builds like using logfile size / status / days/ intervals days / build num / logfile regular expression.
Click on Job
Click on Configure
Go to Post-Build Action
Select Discard Old Build
Enter Days to keep build : 2
Max # of builds to keep : 10
Click on Apply and Save
![image](folder/image.png)
```

* Clone the code available in the same repository.
   ```
 * Using git protocol
	First we have to make some changes in /etc/sudoers file.
	Add the line : jenkins ALL=(ALL) NOPASSWD: ALL
	Save the file.
	Click On new item
	Enter the name 
	Select the Freestyle Project
	Click ok 
	Open the Job
	Click on Configure
	Go to Build Section
	Click on Add Build Step
	Select Execute Shell
	Write : cd /home/arpita/Documents/Ninja/
	sudo git clone https://github.com/arpita-hub/GitPractice.git
	Click on Apply and Save.
	![image](folder/image.png)
```
```
    * Using ssh protocol
```
* Update above jenkins job so that it should be able to identify if there is a code commit in last 5 minutes it should get triggered.

```
Install Plugin : GitHub Integration
Click on Configure
Go to General Section : Select GitHub Project
			Paste GitHub Project Url

Go to Source Code Management : Select Git
				Enter the Url of GitHub Project

Go to Build Triggers : GitHub Hook trigger for GITScmPolling.

Go to GitHub Website : Go to Settings 
			Select Webhooks
			Add Webhooks
```

* Enable colored console output

```
Install AnsiColor Plugin
	Adds ANSI coloring to the Console Output.
Click on Job
Click on Configure
Go to Build Environment Section
	Select Color ANSI Console Output
	ANSI color map : vga
Click on Apply and Save

![image](folder/image.png)
```
### Good to Do
* Clone the code available in the same repository only if there is changes in *java* folder and only this folder should be checked out.
* Integrate above Jenkins job to integrate with GitLab so that any commit in last 5 minutes will trigger this Jenkins job
* Summarize all important Additional checkout behaviour

## Summary
In this section we have gone through various options of freestyle Jenkins job.

