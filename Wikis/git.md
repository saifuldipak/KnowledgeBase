 ### Non fast forward rejection
 ! [rejected]        main -> main (non-fast-forward)  
error: failed to push some refs to 'https://github.com/saifuldipak/managepdf.git'  
hint: Updates were rejected because the tip of your current branch is behind  
hint: its remote counterpart. Integrate the remote changes (e.g.  
hint: 'git pull ...') before pushing again.  
hint: See the 'Note about fast-forwards' in 'git push --help' for details. 

**Probable cause 1**  
When you try to push into a repository nobody else pushes into. After you push commit to remote repo and then replace it with "git commit --amend", In such a case, and only if you are certain that nobody in the meantime fetched your earlier commit (and started building on top of it), you can run "git push --force" to overwrite it. In other words, "git push --force" is a method reserved for a case where you do mean to lose history.