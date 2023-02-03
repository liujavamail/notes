set nocompatible
filetype off

set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
"Plugin 'ctrlpvim/ctrlp.vim'
Plugin 'junegunn/fzf', { 'do': { -> fzf#install() } }
Plugin 'junegunn/fzf.vim'
Plugin 'airblade/vim-gitgutter'
Plugin 'vim-scripts/ZoomWin'
Plugin 'scrooloose/nerdtree'
Plugin 'vim-ruby/vim-ruby'
Plugin 'tpope/vim-endwise'
"Plugin 'flazz/vim-colorschemes'
Plugin 'tpope/vim-rails'
Plugin 'scrooloose/nerdcommenter'
Plugin 'vim-airline/vim-airline'
Plugin 'vim-airline/vim-airline-themes'
"Plugin 'vim-syntastic/syntastic'
Plugin 'bronson/vim-trailing-whitespace'
Plugin 'nathanaelkane/vim-indent-guides'
Plugin 'fatih/vim-go'
Plugin 'powerline/fonts'
Plugin 'justinmk/vim-sneak'
Plugin 'majutsushi/tagbar'
"Plugin 'szw/vim-tags'
Plugin 'roxma/nvim-yarp'
"Plugin 'ervandew/supertab'
Plugin 'thoughtbot/vim-rspec'
"Plugin 'Shougo/deoplete.nvim', { 'do': ':UpdateRemotePlugins' }
Plugin 'neoclide/coc.nvim', {'branch': 'release'}
Plugin 'joshdick/onedark.vim'

call vundle#end()            " required
filetype plugin indent on    " required

set backspace=2

set number
set relativenumber
set tabstop=2
set shiftwidth=2
set shiftround
set expandtab
set mouse=a

"syntax enable
syntax on
"set background=dark
"set background=light
"colorscheme github
"colorscheme desert
"colorscheme molokai
colorscheme onedark
"colorscheme solarized
"colorscheme PaperColor
"colorscheme neodark
"colorscheme gruvbox
"

" fzf config
nnoremap <silent> <Leader>ag :Ag <C-R><C-W><CR>
nnoremap <silent> <c-p> :Files <CR>
let g:fzf_preview_window = ''
" fzf config

let g:deoplete#enable_at_startup = 1
let g:solarized_termcolors=256
let g:neodark#background = '#202020'
let g:vim_tags_auto_generate = 1
map <C-n> :NERDTreeToggle<CR>



" rspec相关配置
map <Leader>t :call RunCurrentSpecFile()<CR>
map <Leader>s :call RunNearestSpec()<CR>
map <Leader>l :call RunLastSpec()<CR>
map <Leader>a :call RunAllSpecs()<CR>

set completeopt-=preview
autocmd BufWritePre * %s/\s\+$//e
autocmd Filetype go setlocal expandtab tabstop=4 shiftwidth=4 softtabstop=4
let g:airline#extensions#tabline#enabled = 1

" coc.nvim配置
nmap <silent> [g <Plug>(coc-diagnostic-prev)
nmap <silent> ]g <Plug>(coc-diagnostic-next)
nmap <silent> gd <Plug>(coc-definition)
nmap <silent> gy <Plug>(coc-type-definition)
nmap <silent> gi <Plug>(coc-implementation)
nmap <silent> gr <Plug>(coc-references)
set hidden
inoremap <silent><expr> <TAB>
      \ pumvisible() ? "\<C-n>" :
      \ <SID>check_back_space() ? "\<TAB>" :
      \ coc#refresh()
"nmap <silent> <C-b> :call CocAction('jumpDefinition', 'tab drop')<CR>
