Learning Github Some More

git init
git add <file>
git commit

git remote add origin
git push origin master

# Workflow
Your local repository consists of 3 trees maintained by git.
+ Working Directory
+ Index
+ Head

## Working Directory
Holds the actual files

## Index
Acts as a staging area

## Head
Points to the last commit you've made

# Add and Commit
Propose changes (add files to the **Index**) using:
```git add <filename>
```

To actually commit these changes use:
```git commit -m "commit message"
```

Now the file is committed to the **Head** but not in your remote repository yet

## Pushing Changes ##
Your changes are now in the **Head** of your local working copy. To send those changes to your remote repository, execute:
```git push origin master
```

change *master* to whatever branch your want to push your changes to

If you want to connect ytour local repository to a remote server, you need to add it with:
```git remote add origin <server>
```

## Branching
Branches are used to develop features in isolation from one another. The *master* branch is the default branch when you create a repository. Use other branches for development and merge them back to the master branch upon completion.

Create a new branch named "feature_x" and switch to it using:
```git checkout -b feature_x
```

Switch back to the master branch
```git checkout master
```

Delete the branch
```git branch -d feature_x
```

A branch is not available to others unless you push the branch to your remote repository as so:
```git push origin <branch>
```

## Update and Merge
To update your local repository to the newest commit execute:
```git pull
```
in your working directory to *fetch* and *merge* remote changes.

To merge another branch into your active branch use
```git merge <branch>
```
In both cases git tries to auto-merge changes. Not always possible. Sometimes results in *conflicts* You'll need to merge those manually by editing the files shown by git. After changing you need to makr them as merged with
```git add <filename>
```

## Replace Local Changes
In case you did something wrong you can replace local changes using the command:
```git checkout -- <filemame>
```
This replaces the changes in your working tree with the last content in **Head**. Changes already added to the *Index* as well as new files will kept.

If you instead want to drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it like this:
```git fetch origin
git reset --hard origin/master
```

## Describing the project to others
What is the name of the repository?


What is the name of the script?
- rem.py

What does it do?
This tool runs DeepDream neural visualization on live video input and generates live output. Its a magic mirror that reflects the alien inside the familiar.

How does it work
DeepDreaming is computationally intensive, and the Caffe/OpenCV/CUDA backbone of the process is
The script captures a video frame and will dream about that frame indefinitely, passing the output of the last cycle as the input of the next cycle, zooming in slightly each time. The real world soon disappears.


Why did I make it?
- 


*Writing Samples*
DeepDream
-------------
This repository contains IPython Notebook with sample code, complementing Google Research blog post about Neural Network art. See original gallery for more examples.

DeepDream Animator
-------------
This tool helps to create animations with deepdream. Extract frames from videos, process them with deepdream and then output as new video file. Frame blending option is provided, to ensure "stable" dreams across frames. A preview function make rapid iterations possible. Optionally guided dreaming & optical flow can be used.

Requirements
-------------
Python
Caffe (and other deepdream dependencies)
FFMPEG
CV2 (if you use optical flow)

How to
-------------
Extract Video
python dreamer.py --input myvideo/video.mp4 --output myvideo --extract 1

Run DeepDream
python dreamer.py --input myvideo --output myvideo/frames

Create Video
python dreamer.py --input myvideo/frames --output myvideo/deepdreamvideo.mp4 --create 

Credits
-------------
Gary Boodhoo | sciencefictionthriller.com | @skinjester




# Vocabulary
Local Working Copy
Remote Repository
Branch
Active Branch
Head
Add
Commit
Push
Pull
Merge
Conflicts


