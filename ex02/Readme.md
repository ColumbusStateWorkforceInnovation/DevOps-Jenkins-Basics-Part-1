For this exercise, we will set up a simple job that pulls and executes a script from GitHub.  This exercise isn't terribly difficult, but it is the root of CI/CD.  If you can pull down and execute scripts, you can build and deploy an application from a pipeline.  In week 10, we will use Jenkins and Maven to build and test an application from configurations.

* From the Jenkins dashboard, click "Create a job"
* Name your job any name you like and select freestyle project.  Click OK to proceed to the job setup
* In this exercise, we'll configure our job from the UI.  Remember that all of these configurations can be set in code as well.
* Go to the Source Code Management section and set the job to pull the assignment Git repo:
  * https://github.com/ColumbusStateWorkforceInnovation/Infrastructure-Automation-Jenkins-Basics
* Since this is a public repository, you won't need to set up credentials at this time.  Leave the branch configuration set to master.
* Configuring this repository adds a step to the beginning of the build for Jenkins to pull the repository for your build down to its workspace.  Commonly, this feature is used to pull down application code and build scripts for build jobs.

### Question 1 (Provide your answers in ex02Questions.txt):

Review the options under Build Triggers.  Why might you want to set up your build to trigger "after other projects are built" or use a GitHub webhook to poll git?

## Instructions

1. Now, scroll down to the Build section to add a build step
2. Select "execute shell" 
3. Add `./ex02/helloworld.sh` to the textbox that appears
4. At this point, we could configure many other build steps and post-build steps.  You can play with these steps and settings before proceeding.
5. Save the build job

### Question 2:

Review the options under Build Environment.  Why might you want to delete the workspace before the build starts?  

## Instructions

6. Now, let's execute the hello world job you just created!  You should be on the project screen.  You can navigate to here from the dashboard by clicking the name of the job you just created.
7. You can always click "Configure" to change any of the settings we just set up.
8. Click Build Now to kick off your build
9. You'll see the build history populate with the results of your build every time you start the build job.  If your build was successful, you'll see a blue circle beside the build number, and if it failed, you will see a red circle. 
10. You can see the details of your build by clicking on the number of the execution (ex: #1)
11. From this screen, let's look at your build in detail.
12. Click on Git Build Data to see what was pulled down into your workspace at the start of your job

### Question 3:

Where will the script we specified run when the build job is executed?  (Recall that this is a dockerized Jenkins instance)

## Instructions

13. Click on Console output to see the output of each step of your build, including output of scripts that were run.  This view is incredibly valuable when troubleshooting builds
14. If you have any status other than SUCCESS in the last step of your job here, you will need to go back and reconfigure your job so that it builds successfully.  Jenkins will provide you with failure details in this console output if there are problems.
15. Edit your job until you have a SUCCESS message at the end of your build output
16. Congratulations, you've set up a rudimentary Jenkins job!  We'll build on this experience next week to build and test a Java application.

### Question 4:

Paste the revision GUID that your job pulled down as the answer to this question.

### Question 5:

Paste the last 4 lines of your successful build's console output as the answer to this question


