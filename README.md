# CEMFI GitHub Workshop 2022

## Slides
- [HTML](https://kazuyanagimoto.com/github-workshop2022/)
- [PDF](https://kazuyanagimoto.com/github-workshop2022/index.pdf)

## Preparation
1. Create a GitHub Account 
1. Download the following tools
1. Open VS Code and log in to GitHub (click the bottom-left icon of a human)

With the CEMFI email address, you can get the student developer pack.

### Tools
- [VSCode](https://code.visualstudio.com/) (Editor and GUI tools for GitHub)
- [DVC](https://dvc.org/) (Version Control Tools for Data)

You might need to reboot your computer after the installation.
DVC does not have a GUI application. 
Even if the installation succeeded, you won't see any icon in the menu.

I think most PCs have git by default. To make sure, run this in the command line
```{shell}
git --version
```

If you don't have it, downloading [GitHub Desktop](https://desktop.github.com/)
is one of the easiest ways to download git.


## Cheet Seet
### Initialize Project
1. Create a Remote Repository
1. Clone it to your local machine (from VS Code)
1. Prepare the folder in Google Drive (and copy the folder code)
1. Setup the remote of DVC

```
dvc init
dvc remote add --default myremote gdrive://GDRIVE_FOLDER_CODE
```

### WorkFlow
#### 1. Sync Local Repository (Remote to Local)
```
git switch main
git pull origin main
dvc pull
```
#### 2. Work (Local)
1. Checkout to _dev_ branch
```
git checkout -b "dev"
```
2. Write Codes
#### 3. Commit (Local)
```
dvc add -R data
git add .
git commit -m "hogehoge"
```
#### 4. Push and Pull Request (Local to Remote)
1. Push to _dev_ branch in the remote repository
```
git push origin dev
```
2. Open GitHub remote repository
3. Create a Pull Request (_dev_ -> _main_)
4. Confirm merge and delete _dev_ branch

#### 5. Sync Local Repository and Delete Developing Branch (Remote to Local)
```
git switch main
git pull origin main
git branch -d dev
```

#### 6. Push to DVC Remote Storage
```
dvc push
```