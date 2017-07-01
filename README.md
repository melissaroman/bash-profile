# Pretty Colors!
```
BLACK="\033[0;30m"  
DARK_GRAY="\033[1;30m"  
LIGHT_GRAY="\033[0;37m"  
BLUE="\033[0;34m"  
LIGHT_BLUE="\033[1;34m"  
GREEN="\033[1;32m"  
LIGHT_GREEN="\033[0;32m"  
CYAN="\033[0;36m"  
LIGHT_CYAN="\033[1;36m"  
RED="\033[1;31m"  
LIGHT_RED="\033[0;31m"  
PURPLE="\033[0;35m"  
LIGHT_PURPLE="\033[1;35m"  
BROWN="\033[0;33m"  
YELLOW="\033[1;33m"  
LIGHT_YELLOW="\033[0;33m"  
WHITE="\033[1;37m"  
COLOR="\033[00m"
```

# git auto-complete
```
if [ -f ~/.git-completion.bash ]; then
  . ~/.git-completion.bash
fi
```

# Print Red or Green Depending on Status of Current git Repo
```
function parse_git_dirty {
  [[ $(git status 2> /dev/null | tail -n1) != "nothing to commit, working tree clean" ]] && (echo -e "$RED") || echo -e "$GREEN"
}
```

# Print Name of git Branch
```
function parse_git_branch {
  git symbolic-ref HEAD 2> /dev/null | awk -F / '{print "", $NF}'
}
```

# Custom Command Line
```
export PS1="[\[$CYAN\]\u\[$COLOR\]:\[$LIGHT_YELLOW\]\W\[\$(parse_git_dirty)\]\$(parse_git_branch)\[$COLOR\]] $ "
```

# Colors ls should use for folders, files, symlinks etc.
```
export LSCOLORS=gxfxcxdxbxegedabagacad
```

# Force ls to use colors (G) and use humanized file sizes (h)
```
alias ls='ls -Gh'
```

# Force grep to always use the color option and show line numbers
```
export GREP_OPTIONS='--color=always'
```

# nom bom
```
alias nom='npm cache clear && rm -rf node_modules && npm install'
alias bom='bower cache clean && rm -rf bower_components && bower install'
alias nombom='npm cache clear && bower cache clean && rm -rf node_modules bower_components && npm install && bower install'
```

# Ember code coverage
```
alias ets='COVERAGE=true ember test --server'
```
