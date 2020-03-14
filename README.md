# GIT tutorial in Altium Designer

**NOTE: Make sure you use at least AD v18.0.11!!**

**NOTE2: Install GIT for findows from [here](https://gitforwindows.org/ "here")**

1. Initialize a repository
2. Go to the AD project directory
3. Right-click and select *GIT Bash Here*
4. Once the console popped-up, generate the SSH key as expained in the following [tutorial](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent "tutorial")
5. Providing that SSH configuraion is already done, close AD and put the following commands:
```bash
git init
git remote add <origin_name> <origin_url>
git add .
git rm -r --cached __Previews  
git rm -r --cached History 
git rm -r --cached Project\ Logs*/
git rm -r --cached Project\ Outputs*/
git rm -r --cached *.PcbDoc.htm
git rm -r --cached **/*.ldb
```
6. Create .gitignore file and add the following code:
```bash
### Altium ###
# Previews Folders
**/__Previews/

# History Folders
**/History/*

# Project Logs
Project\ Logs*/

# Project Outputs
Project\ Outputs*/

# Auto-conversion notices
*.PcbDoc.htm

# Access lock file for dbLib sources
**/*.ldb
```
7. Add .gitignore using the following commands:
```
git add .gitignore
```
8. Now, you can check all tracked files by prompting this command:
```
git ls-files
```
9. Add initial commit:
```
git commit -m "Initial commit"
```
10. Push changes:
```
git push
```
