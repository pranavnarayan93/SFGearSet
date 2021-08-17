# Department of Education , South Australia - Salesforce Repository

This readme gives a broad overview of the branching and deployment model adopted.

## Part 1: Branching Model
Branching strcutre can be found at https://systempartners.atlassian.net/wiki/spaces/SDFESA/pages/1347879092/Branching+Structure . 

### Part 2: Deployment Model
Environment Strcuture can be found at https://systempartners.atlassian.net/wiki/spaces/SDFESA/pages/1347551316/Environment+Structure

### Part 3 : CI / CD Process
Pre-Requisites:
VS Code
SFDX – Latest Version
Source Tree(recommended)/ GitHub Desktop or CLI to run Git 

Repository URL: git clone https://pranavnarayandxc@bitbucket.org/systempartners/dfe-south-australia.git
Development Branch: Development 
Naming Conventions:
Feature : feature/*
BugFix : bugfix/*


Setup and Process:
Open the directory where you want to clone the remote repo and type the command:

git clone https://pranavnarayandxc@bitbucket.org/systempartners/dfe-south-australia.git. This will result in a directory like this

Check out a new feature branch (naming convention is feature/*) from the Development branch

Create a default scratch org in the same directory

Push the source into the scratch org and override conflicts(This is to have all the last updates on the development branch on to the scratch org).

Continue with the development and unit testing

Pull all your changes to the local directory using SFDX

The changes will be tracked on the Git

Keep committing the changes to your feature branch.

Once all the changes are committed push the branch to the remote repository

When you push changes to the feature branch, a pipeline will run which will create a scratch org and deploy the changes and run all tests to ensure coverage and failures.

Once that’s validated, raise a PR to merge into the development branch

The development branch will have a check run that will validate the deployment into the Merge Sandbox.

Once the check is complete, the approver once merges the PR, the change will deploy into the merge sandbox. Continue testing

If a bug is found during the testing in merge or SIT, create a branch with the naming convention bugfix/*.
