# FluShotLearning

## Anaconda 
install anaconda (used for running git commands, jupyter server, installing packages, etc.)

## VS Code
install VS Code with extensions - Jupyter, Jupyter Keymap, Git Graph, Pylance, Python

## Git
```
git clone https://github.com/Shegy2106/FluShotLearning.git
```

// for versioning use git add, git commit -m, git push, etc...

// rewrite hooks/pre-commit.sample to pre-commit with these lines 

```
#!/bin/sh
jupyter nbconvert --ClearOutputPreprocessor.enabled=True --inplace Best_with_fills.ipynb
echo "pre-commit blabla"
git add .
```


// config file should be like this

```
[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
[remote "FluShotLearning"]
	url = https://github.com/Shegy2106/FluShotLearning.git
	fetch = +refs/heads/*:refs/remotes/FluShotLearning/*
[branch "master"]
	remote = FluShotLearning
	merge = refs/heads/master
[filter "remove-notebook-output"]
    clean = "jupyter nbconvert --clear-output --to=notebook --stdin --stdout --log-level=ERROR"
[diff]
    tool = vscode
[difftool "vscode"]
    cmd = code --wait --diff $LOCAL $REMOTE
```
    
// make new file info/attributes.txt with contents

```
*.ipynb filter=remove-notebook-output
```

## Jupyter 

```
jupyter notebook --NotebookApp.allow_origin='https://colab.research.google.com' --port=8888 --NotebookApp.port_retries=0
```

## MLFlow (must be started before notebook is running) 
// open anaconda prompt, change directory path to project folder and execute
// use linux commands (cd, ls)

```
mlflow ui // (starts on localhost:5000)
```




