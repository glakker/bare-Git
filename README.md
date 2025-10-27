# bare-Git
bare Git for dotfiles howto

## Setup
1. Create bare Git repo
```
git init --bare $HOME/dotgit
```

2. Add alias to .bashrc
```
alias dotgit='git --git-dir=$HOME/dotgit/ --work-tree=$HOME'
```

3. Tell Git that this repo should not display all untracked files 
```
dotgit config status.showUntrackedFiles no
```

4. Setup GitHub repo
```
dotgit remote add origin name@github.com:username/reponame
```

5. Add files to repo (with full path)
```
dotgit add -config/dirname/filename
dotgit add -config/dirname/
```

6. Commit
```
dotgit commit -m "remark"
```

7. Push
```
dotgit push origin master
```
(Token is needed to push, generate on GitHub, use as passwrd.)

If cannot push because of README.md on github:
```
dotgit fetch origin
dotgit merge origin/master --allow-unrelated-histories
```


## Operations

Check status
```
dotgit status
```
If there are changes then commit (6.) and push (7.)

Remove file frome repo
```
dotgit rm <file>
dotgit commit -m "Remove file"
```

List files added
```
dotgit ls-files
```

Check config
```
dotgit config --list
```

Edit config
```
dotgit config --edit
```

Change email
```
dotgit config --global user.email "you@example.com"
```

