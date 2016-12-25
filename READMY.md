# Руководство по vim

Начинать изучение vim принято с vimtutor, для этого в консоли нужно набрать `vimtutor`, но я рекомендую переходить к vimtutor после этой статьи [Vim : Режимы](http://rus-linux.net/MyLDP/BOOKS/Vim/prosto-o-vim-07.html)

## Игры vim

[http://vim-adventures.com/](http://vim-adventures.com/)

[http://vimgolf.com/](http://vimgolf.com/)

`di"` - удаление текста внутри двойных кавычек

`di'` - удаление текста внутри одинарных кавычек

Находясь на слове, нажимаем `*`, чтобы найти похожие слова в документе

## .vimrc
```
set number "нумерация строк
set expandtab "заменяем табы на пробелы
"set tabstop=2 "размер таба - 2 пробела
   
set hlsearch "подсветка поисковых резкльтатов
set incsearch "инкрементальный поиск
```
## Менеджеры плагинов vim

[https://github.com/VundleVim/Vundle.vim](https://github.com/VundleVim/Vundle.vim)

[https://github.com/tpope/vim-pathogen](https://github.com/tpope/vim-pathogen)

[https://github.com/junegunn/vim-plug](https://github.com/junegunn/vim-plug)

### Установка vim-plug

#### Для установки vim-plug введите следующую команду в консоли
```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
#### Минимальная конфигурация .vimrc
```
call plug#begin('~/.vim/plugged')

Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }

call plug#end()
```

Добавляем этот код в начало нашего .vimrc, в итоге получаем это

```
call plug#begin('~/.vim/plugged')

Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }

call plug#end()

set number "нумерация строк
set expandtab "заменяем табы на пробелы
"set tabstop=2 "размер таба - 2 пробела
   
set hlsearch "подсветка поисковых резкльтатов
set incsearch "инкрементальный поиск
```
#### Устанавливаем плагины
1. `:w` - сохраняем файл
2. `:source` ~/.vimrc - вычитываем файл
3. `:PlugInstall` - устанавливаем плагины

#### Добавляем mapping для нашего плагина
```
"mappings

map <C-n> :NERDTreeToggle<CR>
```
Получаем такой .vimrc
```
call plug#begin('~/.vim/plugged')

Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }

call plug#end()

set number "нумерация строк
set expandtab "заменяем табы на пробелы
"set tabstop=2 "размер таба - 2 пробела
   
set hlsearch "подсветка поисковых резкльтатов
set incsearch "инкрементальный поиск

"mappings

map <C-n> :NERDTreeToggle<CR>
```
#### Добавляем подсветку кода
```
syntax on
```
Получаем такой .vimrc
```
call plug#begin('~/.vim/plugged')

Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }

call plug#end()

set number "нумерация строк
set expandtab "заменяем табы на пробелы
"set tabstop=2 "размер таба - 2 пробела
syntax on
   
set hlsearch "подсветка поисковых резкльтатов
set incsearch "инкрементальный поиск

"mappings

map <C-n> :NERDTreeToggle<CR>
```
