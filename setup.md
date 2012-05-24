# Setup

## Homebrew

## GCC

## BASH prompt

### show git branch and activity in prompt

The modifications that Blake is using in his bash prompt. Exptracted below


    function parse_git_deleted {
      [[ $(git status 2> /dev/null | grep deleted:) != "" ]] && echo "-"
    }
    function parse_git_added {
      [[ $(git status 2> /dev/null | grep "Untracked files:") != "" ]] && echo '+'
    }
    function parse_git_modified {
      [[ $(git status 2> /dev/null | grep modified:) != "" ]] && echo "*"
    }
    function parse_git_dirty {
      # [[ $(git status 2> /dev/null | tail -n1) != "nothing to commit (working directory clean)" ]] && echo "ÃÂÃÂÃÂÃÂ¢ÃÂÃÂÃÂÃÂÃÂÃÂÃÂÃÂ "
      echo "$(parse_git_added)$(parse_git_modified)$(parse_git_deleted)"
    }
    function parse_git_branch {
      echo "$(parse_git_dirty)$(__git_ps1 '%s')"
    }

    Black='\e[0;30m'
    Red='\e[0;31m'
    Green='\e[0;32m'
    Yellow='\[\e[0;33m\]'
    Blue='\e[0;34m'
    Purple='\e[0;35m'
    Cyan='\[\e[0;36m\]'
    White='\[\e[0;97m\]'

    export PS1="\u@\h${Cyan}[\W] ${Yellow}\$(parse_git_branch)${White}\$ "



