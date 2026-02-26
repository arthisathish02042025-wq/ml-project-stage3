Commands:
Create a folder:
C:\Arthi>mkdir ml-project

C:\Arthi>cd ml-project

C:\Arthi\ml-project>cd
C:\Arthi\ml-project

Git Initialization:
C:\Arthi\ml-project>git init
Initialized empty Git repository in C:/Arthi/ml-project/.git/

Creating Python and README files:
C:\Arthi\ml-project>echo "train.py file" > train.py

C:\Arthi\ml-project>echo "predict.py file" > predict.py

C:\Arthi\ml-project>echo "utils.py file" > utils.py

C:\Arthi\ml-project>echo "README file" > README.md

Checking Git Status:
C:\Arthi\ml-project>git status
On branch master

Adding python files to git:
C:\Arthi\ml-project>git add train.py

C:\Arthi\ml-project>git add utils.py

Committing changes to Git repository local:
C:\Arthi\ml-project>git commit -m "Add training script and utilities"

Shows the git commit status:
C:\Arthi\ml-project>git show  --name-only
commit af0317fec89fdd51e452d68dd56cf577845a3b0b (HEAD -> main)
Author: Arthi Saravanan <a0s0u3p@homeoffice.wal-mart.com>
Date:   Thu Feb 26 18:07:08 2026 +0530

    Add training script and utilities

train.py
utils.py

Cloning the Github repository with the git in local:
C:\Arthi\ml-project>git remote add origin https://github.com/arthisathish02042025-wq/ml-project.git

Shows the Github repository link whether connected and listed fine:
C:\Arthi\ml-project>git remote -v
origin  https://github.com/arthisathish02042025-wq/ml-project.git (fetch)
origin  https://github.com/arthisathish02042025-wq/ml-project.git (push)

Push the committed changes to the Github:
C:\Arthi\ml-project>git push -u origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (4/4), 314 bytes | 314.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/arthisathish02042025-wq/ml-project.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
