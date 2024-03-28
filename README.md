# Unity Project Setup (PLEASE READ)

Before you start, follow these instructions:

## Make sure Git LFS is installed
When you clone this repository, remember to make sure Git LFS is installed. Then clone this repo.

## Modify your GLOBAL .gitconfig
Not everyone on your team may have the same path to UnityYAMLMerge (i.e. diffrent operating systems or install locations). Because of this, we suggest you modify your local config to define the "UnityYAMLMerge" merge tool that this repository's .gitconfig points to. To do this:

1. Find and open your local config file inside of the hidden git folder `.git\config`:
2. Identify your version of unity (e.g. `2022.3.19f1`). This will replace the word `VERSION` in the paths commented below depending on your OS. Then, add the following text to the bottom of the file, replacing `<path to UnityYAMLMerge>` with the one specific to your OS and Unity version. For instance, in Unity version 2022.3.19f1 on Windows, the last line should be `cmd = 'C:\\Program Files\\Unity\\Hub\\Editor\\2022.3.19f1\\Editor\\Data\\Tools\\UnityYAMLMerge.exe' merge -p "$BASE" "$REMOTE" "$LOCAL" "$MERGED"`
```bash
[mergetool "unityyamlmerge"]
    trustExitCode = false
    #Replace <path to UnityYAMLMerge> in the next line with the following default locations (may be diffrent depending on your Unity installation location)
    # Installs using the Unity Hub (Default):
    # Win: C:\\Program Files\\Unity\\Hub\\Editor\\VERSION\\Editor\\Data\\Tools\\UnityYAMLMerge.exe
    # MacOS: /Applications/Unity/Hub/Editor/VERSION/Unity.app/Contents/Tools/UnityYAMLMerge
    # Linux: /home/USERNAME/Unity/Hub/Editor/VERSION/Editor/Data/Tools/UnityYAMLMerge
    cmd = '<path to UnityYAMLMerge>' merge -p "$BASE" "$REMOTE" "$LOCAL" "$MERGED"
```

## Opening the Project
This project was created using `2020.3.17f1`. When you open this project in Unity, Unity may say that it needs to upgrade the project. Given this is a bare-bones project, this is a safe action and you may allow Unity to continue. Overall, your entire team should be using the **same version of Unity**.

## Adding pre and post-commit scripts
Download the scripts from the link below and paste them into `<your_repo>/.git/hooks/`
- Pre-commit: https://github.com/NYUGameCenter/Unity-Git-Config/blob/master/pre-commit
- Post-commit: https://github.com/NYUGameCenter/Unity-Git-Config/blob/master/post-merge

## Starting a new project or adding version control to an old one?
If you are starting a new project you can start working now, but if you are adding version control to an old one follow these steps:
1. Paste your project files into this repository on your local machine. 
2. Open the project on the target Unity version, so all the files are modified as necessary. 
3. If you had Unity Version Control (formerly Collab or Plastic SCM), disable it now.
4. Save your project and close Unity.
5. Delete left over files from Unity Version Control like x.meta.private or y.meta.private.meta (some files may be hidden so enable see hidden files)
6. Commit and push.
7. If you are having issues with .meta files check and modify your gitignore or make sure there are no empty folders. 

