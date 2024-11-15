**Describe the bug**
Operation not permitted Error caused by  special characters in the repo directory or files.When I trying pulling my repo in which directory contains a '?' of one directoy name,the Operation not permitted Error occured,the same behavoir like https://github.com/maks/MGit/issues/708 
There is a repo aim to automatically backup and sync my study notes written by markdown.Recently , I try to rename a directory and typed a '?' in it by mistake , it was automatically commited and pushed to my repo in github,for that day I was so busy for my course so that I ignored that '?'

the next day when I try to sync my study notes in my phone by MGit ,Operation not permitted Error occured .
when I delete the '?' , everything return to normal.

Although using special characters in the repo directory or files is a bad behavoir of user, is there any better way to handle that abnomal exception ? 

**To Reproduce**
Steps to reproduce the behavior:
here is a test_repo to reproduce that problem:
https://github.com/mamashende/test_repo

clone git@github.com:mamashende/test_repo.git
by MGit



using MGit to clone this repo in my phone , Operation not permitted Error 
**Expected behavior**
A clear and concise description of what you expected to happen.

**Screenshots**
If applicable, add screenshots to help explain your problem.

**Smartphone (please complete the following information):**
 - Device: [Redmi K40]
 - OS: [Android 13]
 - App Version [1.7.0]

**Additional context**
Add any other context about the problem here.



**Describe the bug**  
Encountered an "Operation not permitted Error" due to special characters in the repo directory or files. While attempting to pull a repository containing a '?' in one of the directory names, the "Operation not permitted Error" occurred, similar to the behavior reported in [https://github.com/maks/MGit/issues/708](https://github.com/maks/MGit/issues/708).

The repository in question serves the purpose of automatically backing up and syncing my study notes written in Markdown. Recently, I unintentionally included a '?' in the directory name while renaming it. This change was automatically committed and pushed to my GitHub repository. Due to my busy schedule that day, I overlooked the presence of '?'.

The following day, while trying to sync my study notes on my phone using MGit, the "Operation not permitted Error" occurred. Upon removing the '?', everything returned to normal.

While using special characters in the repository directory or files is discouraged, is there a more robust way to handle such abnormal exceptions?

**To Reproduce**  
Steps to reproduce the behavior:

1. Clone the test repository to replicate the issue: [https://github.com/mamashende/test_repo](https://github.com/mamashende/test_repo)
2. Use MGit to clone git@github.com:mamashende/test_repo.git on your smartphone.
3. Observe the "Operation not permitted Error" when attempting to clone the repository using MGit.


**Smartphone (please complete the following information):**

- Device: Redmi K40
- OS: Android 13
- App Version: 1.7.0


