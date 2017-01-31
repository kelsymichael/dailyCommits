# Table of contents
1. [SublimeText](#sublimeText)
2. [Terminal](#terminal)
    1. [.bash_profile](#bashProfile)
    2. [.vimrc](#vimrc)

---

## Sublime Text <a name='sublimeText'></a>
![sublimetext preview](/photos/sublimetext.png)




#### open sublime from terminal 
```bash
ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl
```

#### settings > user
```json
{
	"color_scheme": "Packages/User/SublimeLinter/itg.dark (SL).tmTheme",
	"font_size": 15,
	"highlight_line": true,
	"ignored_packages":
	[
		"CSS",
		"CSS Color Converter",
		"Javascript"
	],
	"ignored_words":
	[
		"––––––––––––––––––––––––––––––––––––––––––––––––––",
		"Firebase"
	],
	"itg_small_tabs": true,
	"tab_size": 2,
	"theme": "Material-Theme.sublime-theme",
	"translate_tabs_to_spaces": true,
	"update_check": true
}
```

## Terminal <a name='terminal'></a>
---
### .bash_profile <a name='bashProfile'></a>
![terminal preview](/photos/terminal.png)




```bash
print_before_the_prompt () {
	printf "\n $txtpur%s $txtrst" "$PWD" 
	}
	
PROMPT_COMMAND=print_before_the_prompt
PS1='\W\n >'
export PATH="/usr/local/git/bin:/usr/local/bin:/usr/bin:/usr/local/sbin:$PATH"
export PATH="/usr/local/Cellar/vim:$PATH"

## start of aliases ##
## folders ##
alias wnotes='cd /Users/kelsymichael/Library/Mobile\ Documents/com~apple~CloudDocs/DirectScale/notes && vim tasklist.md'
alias pgit='cd /Users/kelsymichael/Dropbox/_DevMountain/@personal/personalSite/kelsymichael.github.io && ls'
alias dmt='cd /Users/kelsymichael/Dropbox/_DevMountain/@current && ls'
alias mysite='cd /Users/kelsymichael/Library/Mobile\ Documents/com\~apple\~CloudDocs/Projects/'

## files ##
alias dnotes='cd /Users/kelsymichael/Dropbox/_DevMountain/@personal/dailyCommits/@notes && vim inClass.md'
alias v='vim'
alias vbp='v .bash_profile'

## directory nav ##
alias l1='ls -1'
alias ls='ls -G -F'
alias la1="ls -1 -a" 
alias ..='cd ../'                           # Go back 1 directory level
alias ...='cd ../../'                       # Go back 2 directory levels
alias .3='cd ../../../'                     # Go back 3 directory levels
alias .4='cd ../../../../'                  # Go back 4 directory levels
alias .5='cd ../../../../../'               # Go back 5 directory levels
alias .6='cd ../../../../../../'

## git ##
alias g='git'
alias gloga='git log --graph --oneline --decorate --all' #git showing all b & tag
alias glogns='git log --name-status' #showing only which files been changed
alias glog='git log --pretty=oneline' #preferred view
alias glogg='git log' #git's original default log view

## browser-sync ##
alias bsync="browser-sync start --files '*.html, assets/css/*.css' --server" 

## stylus compiling ##
alias stylusc='stylus -w -u nib stylus/index.styl -o css/'

## colorscheme ##
export CLICOLOR=1
export LSCOLORS=gxBxhxDxfxhxhxhxhxcxcx

txtblk='\e[0;30m' # Black - Regular
txtred='\e[0;31m' # Red
txtgrn='\e[0;32m' # Green
txtylw='\e[0;33m' # Yellow
txtblu='\e[0;34m' # Blue
txtpur='\e[0;35m' # Purple
txtcyn='\e[0;36m' # Cyan
txtwht='\e[0;37m' # White
 
bldblk='\e[1;30m' # Black - Bold
bldred='\e[1;31m' # Red
bldgrn='\e[1;32m' # Green
bldylw='\e[1;33m' # Yellow
bldblu='\e[1;34m' # Blue
bldpur='\e[1;35m' # Purple
bldcyn='\e[1;36m' # Cyan
bldwht='\e[1;37m' # White
 
unkblk='\e[4;30m' # Black - Underline
undred='\e[4;31m' # Red
undgrn='\e[4;32m' # Green
undylw='\e[4;33m' # Yellow
undblu='\e[4;34m' # Blue
undpur='\e[4;35m' # Purple
undcyn='\e[4;36m' # Cyan
undwht='\e[4;37m' # White
 
bakblk='\e[40m'   # Black - Background
bakred='\e[41m'   # Red
badgrn='\e[42m'   # Green
bakylw='\e[43m'   # Yellow
bakblu='\e[44m'   # Blue
bakpur='\e[45m'   # Purple
bakcyn='\e[46m'   # Cyan
bakwht='\e[47m'   # White
 
txtrst='\e[0m'    # Text Reset

## show and hide system files ##
alias showFiles='defaults write com.apple.finder AppleShowAllFiles YES; killall Finder /System/Library/CoreServices/Finder.app'

alias hideFiles='defaults write com.apple.finder AppleShowAllFiles NO; killall Finder /System/Library/CoreServices/Finder.app'

```

### .vimrc <a name='vimrc'></a>
![vim preview](/photos/vim.png)




```vim
syntax on
set background=dark
filetype off                 

colorscheme smyck

set hlsearch
set incsearch
set showmatch

filetype plugin indent on
autocmd Filetype gitcommit setlocal spell textwidth=72

highlight ColorColumn ctermbg=magenta
   call matchadd('ColorColumn', '\%81v', 100)

set hidden
set history=700
set ignorecase
set smartcase
set smarttab
set smartindent
set cursorline
set wildmenu
set nocompatible
set ai
set si

set tabstop=2
set shiftwidth=2
set softtabstop=2
set number
set title
set matchpairs+=<:>

set foldmethod=indent
set foldnestmax=10
set nofoldenable
set foldlevel=1

autocmd vimenter * NERDTree

set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

Plugin 'mattn/emmet-vim'
Plugin 'Valloric/YouCompleteMe'
Plugin 'scrooloose/nerdtree'
Plugin 'tpope/vim-fugitive'
Plugin 'scrooloose/syntastic'
Plugin 'pangloss/vim-javascript'
Plugin 'gmarik/Vundle.vim'
Plugin 'airblade/vim-gitgutter'
Plugin 'kien/ctrlp.vim'
Plugin 'godlygeek/tabular'
Plugin 'plasticboy/vim-markdown'

call vundle#end()

```

## programs to download ##
* [marked 2](http://marked2app.com)
* [PIA - vpn](https://www.privateinternetaccess.com)
* [lingo](https://www.lingoapp.com)
* [CCC](https://bombich.com)
* [CheatSheet](https://www.mediaatelier.com/CheatSheet/)
* [Craft Manager](https://labs.invisionapp.com/craft)
* [Daisy Disk](https://daisydiskapp.com)
* [Dash](https://kapeli.com/dash)
* [FileBot](http://www.filebot.net)
* [Folio](http://folioformac.com)
* [Framer](https://framerjs.com)
* [Grammarly](https://www.grammarly.com)

