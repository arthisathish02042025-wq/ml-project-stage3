Updated the Commands
Detailed Step-by-Step Guide:
To sync work with your teammate, you must follow the Commit → Pull → Push workflow to ensure your local changes are saved before integrating their code.
Step 1: Save Your Work
Command: git add . (add files required to add in git) then git commit
Reason: You currently have uncommitted changes in utils.py and config.py. If you try to pull now, Git might block you to prevent overwriting your work. Committing safeguards your files locally.
Step 2: Sync with Team
Command: git pull origin main (pull the code teammate worked from GitHub and merge it in the local code)
Reason: This downloads your teammate's updates (predict.py, README.md) and merges them into your project. Since your files don't overlap, Git will auto-merge them.
Step 3: Share Your Code
Command: git push -u origin main ->push local code changes from git to GitHub repository.
Reason: Now that your branch has both your changes AND your teammate's changes, it is safe to send everything back to GitHub.

Task: Write a complete workflow guide that explains:

1.	The commands to retrieve your teammate's changes from GitHub
Command: git pull origin main
Scenario:
	git pull origin main -> will pull the predict.py and README.md update code changes done by teammates to git local and then sync it automatically to the code changes in the corresponding files.
This command will pull the code changes from the GitHub and sync it in Git Local to the code directory automatically.
2.	The commands to stage and commit your local changes
Command: git add (file.py)
Scenario:
	git add utils.py
	git add config.py
This command is used to stage the code changes to local git
Command: git commit -m “comments”
Scenario:
	git commit -m “Adding the updated code”
This command is used to commit the code changes to git repository in local
3.	The commands to push your work to GitHub
Command: git push -u origin main
This command will push the code changes from Git to GitHub repository.
4.	What potential issues might arise and how to handle them
If code changes were changed by teammate we need to first pull the code change merge to local and then push the code changes to GitHub else it will throw an error to pull the code change and merge it or else it will not allow to push our code changes.

Detailed Command Sequence
Phase 1: Secure Local Changes
First, you must stage and commit your modified utils.py and new config.py files. This creates a "save point" on your machine. 
bash
1. Stage all changes (modified and new files)
git add .

 2. Save them to your local history
git commit -m "Updated utils.py and added config.py"
Use code with caution.
Phase 2: Integrate Remote Updates
Now, bring in your teammate's work. Because you committed your changes first, Git can safely merge the two timelines. 
 3. Fetch and merge remote changes
git pull origin main
Use code with caution.
•	What happens here: Git will auto-merge the files. You will likely see a screen pop up asking for a "Merge message."
•	How to exit the message screen:
•	If it opens inside the terminal (Vim): Type :wq and press Enter.
•	If it opens VS Code: Save the file and close the tab.
Phase 3: Publish
Finally, upload the combined project state to GitHub so your teammate can see your work. 
bash
4. Send your commits to the server
git push -u origin main
Use code with caution.
Potential Issues & Fixes
1. The "Merge Commit" Editor
When you run git pull, Git often opens a text editor to confirm the merge.
•	Symptom: The terminal freezes and shows Merge branch 'main' of github.com....
•	Fix: This is normal. Just save and close (Type :wq + Enter) to accept the default message.
2. "Updates were rejected"
If you skip Step 2 (Pull) and try to Push immediately, Git will reject it with a non-fast-forward error. 
•	Why: You cannot push unless your local history includes the latest code from the server.
•	Fix: Run git pull origin main to sync, then push again.
3. Unexpected Conflicts
Even though we assumed no conflicts, if your teammate also secretly modified utils.py, Git will pause and say CONFLICT (content).
•	Fix: Open the file in VS Code, choose which code to keep (Accept Incoming or Current), save, and run git commit to finish. 
Commands:
C:\Arthi\ml-project>echo "config file" > config.py
C:\Arthi\ml-project>git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   utils.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .vscode/
        config.py

no changes added to commit (use "git add" and/or "git commit -a")

C:\Arthi\ml-project>git add config.py

C:\Arthi\ml-project>git commit -m "Add training script and utilities"
[main 6f45725] Add training script and utilities
 Committer: Arthi Saravanan <a0s0u3p@homeoffice.wal-mart.com>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 config.py

C:\Arthi\ml-project>git show  --name-only
commit 6f4572506470bcadcd414c40e9843ab2bc508669 (HEAD -> main)
Author: Arthi Saravanan <a0s0u3p@homeoffice.wal-mart.com>
Date:   Thu Feb 26 22:24:48 2026 +0530

    Add training script and utilities

config.py

C:\Arthi\ml-project>git remote add origin https://github.com/arthisathish02042025-wq/ml-project-stage3.git
error: remote origin already exists.

C:\Arthi\ml-project>git remote -v
origin  https://github.com/arthisathish02042025-wq/ml-project.git (fetch)
origin  https://github.com/arthisathish02042025-wq/ml-project.git (push)

C:\Arthi\ml-project>git pull origin main
remote: Enumerating objects: 13, done.
remote: Counting objects: 100% (13/13), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 11 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (11/11), 5.24 KiB | 51.00 KiB/s, done.
From https://github.com/arthisathish02042025-wq/ml-project
 * branch            main       -> FETCH_HEAD
   e1b0b52..c8dd885  main       -> origin/main
Merge made by the 'ort' strategy.
 README.md  | 65 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 predict.py |  1 +
 2 files changed, 66 insertions(+)
 create mode 100644 README.md

C:\Arthi\ml-project>git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   utils.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .vscode/

no changes added to commit (use "git add" and/or "git commit -a")

C:\Arthi\ml-project>git add utils.py

C:\Arthi\ml-project>git commit -m "Add training script and utilities"
[main d7f1665] Add training script and utilities
 Committer: Arthi Saravanan <a0s0u3p@homeoffice.wal-mart.com>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)

C:\Arthi\ml-project>git show  --name-only
commit d7f1665cf77e0e331cb5f9b7346df66106ff5544 (HEAD -> main)
Author: Arthi Saravanan <a0s0u3p@homeoffice.wal-mart.com>
Date:   Thu Feb 26 22:36:26 2026 +0530

    Add training script and utilities

utils.py
C:\Arthi\ml-project>git remote add origin https://github.com/arthisathish02042025-wq/ml-project-stage3.git
error: remote origin already exists.

C:\Arthi\ml-project>git remote -v
origin  https://github.com/arthisathish02042025-wq/ml-project.git (fetch)
origin  https://github.com/arthisathish02042025-wq/ml-project.git (push)


C:\Arthi\ml-project>git push -u origin main
Enumerating objects: 12, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 12 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (8/8), 880 bytes | 73.00 KiB/s, done.
Total 8 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
remote: This repository moved. Please use the new location:
remote:   https://github.com/arthisathish02042025-wq/ml-project-stage3.git
To https://github.com/arthisathish02042025-wq/ml-project.git
   c8dd885..d7f1665  main -> main
branch 'main' set up to track 'origin/main'.


