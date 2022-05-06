## Vimrc with Linux and MacOS
```
" Some basic options
set	number
set relativenumber
set tabstop=4
set shiftwidth=4
set autoindent
syntax on
" use tab to complete the word
inoremap <silent><expr> <TAB>
      \ pumvisible() ? "\<C-n>" :
      \ <SID>check_back_space() ? "\<TAB>" :
      \ coc#refresh()
inoremap <expr><S-TAB> pumvisible() ? "\<C-p>" : "\<C-h>"

function! s:check_back_space() abort
	let col = col('.') - 1
	return !col || getline('.')[col - 1]  =~# '\s'
endfunction
" use enter to chose the complete
inoremap <silent><expr> <cr> pumvisible() ? coc#_select_confirm()
                              \: "\<C-g>u\<CR>\<c-r>=coc#on_enter()\<CR>"

"jump to the error"
nmap <silent> [e <Plug>(coc-diagnostic-prev)
nmap <silent> ]e <Plug>(coc-diagnostic-next)



" vim plug manager
call plug#begin()
Plug 'vim-airline/vim-airline'
Plug 'neoclide/coc.nvim'
call plug#end()

" jump to code navigation.
nmap <silent> gd <Plug>(coc-definition)
nmap <silent> gy <Plug>(coc-type-definition)
nmap <silent> gi <Plug>(coc-implementation)
nmap <silent> gr <Plug>(coc-references)


" set mod key
let mapleader=" "
" split window
map <leader>r :set splitright<CR>:vsplit<CR>
map <leader>b :set splitbelow<CR>:split<CR>

" change window
map <leader>l <C-w>l
map <leader>k <C-w>k
map <leader>h <C-w>h
map <leader>j <C-w>j
map <leader><right> <C-w>l
map <leader><up> <C-w>k
map <leader><left> <C-w>h
map <leader><down> <C-w>j

" cursor style
" Mode Settings

let &t_SI.="\e[5 q" "SI = INSERT mode
let &t_SR.="\e[4 q" "SR = REPLACE mode
let &t_EI.="\e[1 q" "EI = NORMAL mode (ELSE)

" Cursor settings:

"  1 -> blinking block
"  2 -> solid block
"  3 -> blinking underscore
"  4 -> solid underscore
"  5 -> blinking vertical bar
"  6 -> solid vertical bar
```
