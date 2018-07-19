Deleted files from Github still appear in Local Repo

This can happen for a whole lots of reason, expercially when the wildcard * is used to add all files in your local repo.

**Solution**

I found this relatively easy and fast to implement as other steps just  did not work as desired.


1. Click on the files and have them deleted from GitHub console (UI)and ensure to commit these changes.
2. Run git status from the gitbash terminal
3. and Lastly run "git pull"
4. this will show files are being deleted 

For further info: Visit VCS section for technical steps [https://techtrainingworld.wordpress.com](https://techtrainingworld.wordpress.com) 