
# Learning by Doing | Jenkins Setup

## Introduction
In this section we will learn how to work with freestyle jenkins jobs.

## References
* https://www.tutorialspoint.com/jenkins/index.htm

## Assignments
### Must Do
* Create a freestyle job to print "Hello world".

* Create a freestyle job to which take absolute path of a directory then
    * List all files and directories inside that.
    * Print a message "drectory not exist" if directory doesn't exist on file system
    * Print "Inappropriate permissions" if you don't have permissions to list files.
* Update the previously created freestyle job to only retain last 10 build history but not beyond 2 days.
* Clone the code available in the same repository.
    * Using git protocol
    * Using ssh protocol
* Update above jenkins job so that it should be able to identify if there is a code commit in last 5 minutes it should get triggered.
* Enable colored console output
*

### Good to Do
* Clone the code available in the same repository only if there is changes in *java* folder and only this folder should be checked out.
* Integrate above Jenkins job to integrate with GitLab so that any commit in last 5 minutes will trigger this Jenkins job
* Summarize all important Additional checkout behaviour

## Summary
In this section we have gone through various options of freestyle Jenkins job.
