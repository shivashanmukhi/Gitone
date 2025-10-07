Git One-Page Practical Checklist

🧩 1. Setup & Configuration

    git --version                       # confirm git installed
    git config --global user.name "Your Name"
    git config --global user.email "you@example.com"
    git config --list                   # verify settings

📦 2. Starting a Repository

    mkdir project && cd project
    git init                            # start local repo
    echo "# project" > README.md
    git add README.md
    git commit -m "chore: initial commit - add README"


    #Add remote (optional):#

    git remote add origin <repo-url>
    git branch -M main
    git push -u origin main

🌿 3. Branching Workflow

    git branch                          # list branches         
    git checkout -b feature/login       # create & switch branch       
    git add . && git commit -m "feat: add login feature"          
    git checkout main        
    git merge --no-ff feature/login -m "merge: feature/login"       
    git branch -d feature/login         # delete after merge

🔁 4. Daily Update Routine

        git status                          # check changes      
        git pull origin main                # always pull before push      
        git add .                           # stage changes      
        git commit -m "fix: corrected API bug"       
        git push origin main

⚙️ 5. Undo & Recovery

        git restore <file>                  # discard changes     
        git restore --staged <file>         # unstage       
        git checkout HEAD <file>            # restore deleted file      
        git revert <commit_id>              # safely undo commit       
        git reset --hard <commit_id>        # move branch pointer (local use only)

🧠 6. Viewing History

        git log --oneline --graph --decorate --all             
        git show <commit_id>                # details of a commit           
        git diff                            # see unstaged differences    

🧨 7. Handling Merge Conflicts

    Run merge or pull → conflict appears.

Open file → look for:

<<<<<<< HEAD
your changes
=======
incoming changes
>>>>>>> branch-name


    # Edit file manually, remove markers.

    # Save → git add <file> → git commit.

    # Push again.

🔒 8. Security & Hygiene

    echo "*.env" >> .gitignore          # ignore secrets   
    git rm --cached <file>              # remove tracked secret


If secret committed: rewrite history (git rebase -i or git filter-repo) and rotate the key.

🧰 9. Good Practices

    # Commit small, logical changes with clear messages.
    # Pull before push to avoid conflicts.
    # Never git push --force unless you know the impact.
    # Always verify with git log before merging.
    # Use .gitignore for OS or IDE files.
    # Regularly push to remote for backup.

🧮 10. Quick Recovery Commands

    git reflog                          # view all movements (life-saver)
    git cherry-pick <commit_id>         # copy a commit from another branch
    git stash push -m "temp work"       # save unfinished changes
    git stash pop                       # restore them later


💡 Mini Routine Before Any Push

    git pull origin main

    git status

    git add .

    git commit -m "feat/fix/..."

    git push origin main



 