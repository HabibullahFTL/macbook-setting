## For setting your zsh terminl in mac
- From the user root open your terminal
- Type the following command and hit the Return key: ` touch ~/.zshrc ` . 
- That’ll create a .zshrc profile in your user account’s home directory. You can see it under the /User/username/ path in Finder, if you have enabled viewing hidden system files. If not, simply press ` Cmd + Shift + Period (.) ` to show hidden files on your Mac.
- Then open the `.zshrc` file, run the command: `open ~/.zshrc` and then paste the below code & save the file. After that close the terminal and re-open the terminal

```
# ~/.zshrc

# Find and set branch name var if in git repository.
function git_branch_name()
{
  branch=$(git symbolic-ref HEAD 2> /dev/null | awk 'BEGIN{FS="/"} {print $NF}')
  if [[ $branch == "" ]];
  then
    :
  else
    echo '('$branch')'
  fi
}

# Enable substitution in the prompt.
setopt prompt_subst

# Config for prompt. PS1 synonym.
prompt='%2/$(git_branch_name) > '


PROMPT='%F{91}%B%n@%m%f %F{green}%B%~%f %F{27}$(git_branch_name)%f
%F{178}$%f%b '
```


For learning more:
- [How to Customize the zsh Prompt in the macOS Terminal](https://www.makeuseof.com/customize-zsh-prompt-macos-terminal/)
- [Simplest ZSH Prompt Configs for Git Branch Name](https://medium.com/pareture/simplest-zsh-prompt-configs-for-git-branch-name-3d01602a6f33)
