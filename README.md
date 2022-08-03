# TemplateProject (PLEASE READ)

Before you start, follow these instructions:

## Make sure Git LFS is installed
When you clone this repository, remember to make sure Git LFS is installed as shown in class.

## Modify your GLOBAL .gitconfig
Not everyone on your team may have the same path to UnityYAMLMerge (i.e. diffrent operating systems or install locations). Because of this, we suggest you modify your global .gitconfig to define the "unityyamlmerge" merge tool that this repository's .gitconfig points to. To do this:

1. Find and open your global .gitconfig:
- Mac/Linux: In your user "home" directory (e.g. `~/.gitconfig`)
- Windows: In you user directory (e.g. `C:\Users\<YOUR USER IDENTIFIER>\.gitconfig`)
2. Add the following text to the bottom of the file, subbing in the unitymergetool path:
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
