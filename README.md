# Mastering Vim

## Movement

### 字符移动

- `h`,`j`,`k`,`l`: ⬅️ ⬇️ ⬆️ ➡️

### 词移动

- `w` / `b`
  
  - 下一个/上一个词

- `W` / `B`

- `e` / `E`
  
  - 移动到词的末尾

### 行移动

- `0`/`$`
  
  - 移动到行首/尾

- `^`
  
  - 移动到行开头的第一个非空白处

- `5G`, `:5`
  
  - 移动到第5行

### 块移动

- `{ }`
  
  - 上一个/下一个段落

- `[{`, `]}`
  
  - 移动到块的首、尾部

- `%`
  
  - 匹配括号

### 窗口移动

- `H`,`M`, `L`
  
  - 当前窗口的顶部、中间、底部

- `zt`,`zz`, `zb`
  
  - 滑动到顶部、中间、底部

- `C-B`, `C-F`
  
  - 上一页、下一页

- `C-d`, `C-u`
  
  - 前后移动半页

- `gg` / `G`
  
  - 文件的开头/末尾

- `mx` / `'x`
  
  - 标记/跳转到 x 字符

## Ex command

* `:w` : save

* `:wq`, `:x`, `ZZ`: 保存并退出

* `:q` : 退出，quit

* `:q!`, `ZQ`: 强制退出

* 编辑文件
  
  * `:e file` 
  
  * `:o file`:打开文件
- `:saveas file`: 保存文件为
* `:h` :vim help

* `:n`:  跳转到第n行

* Search
  
  *  `*`,`#`: 查找当前光标所在词的位置并标记
  
  * `f - x:` 移动到下一个x字符位置
  
  * `/xxx` : 查找xxx字符
  
  *  `?xxx` : 反向查找xxx字符
  
  * `n` / `N` : 下一个/上一个搜索结果

* `:%s/old/new/g` : 将文档的所有old转为new

* `:%s/old/new/gc` : 带有确认的全局替换操作

* `:noh` ：移除搜索结果的高亮显示

* `:vimgrep /pattern/ {file} `： 在多个文件中搜索pattern

*  `:cn` / `:cp` ： 移动到下一个/上一个匹配位置

* `:copen `: 打开一个新窗口，并且显示所有匹配的内容

## 

----



## Mode

### normal mode

- `ESC`, `C-[`
  
  - 进入标准模式

### Visual mode(标记）

- `v`, `V`
  
  - visual linewise mode

- `C-v`
  
  - visual block mode

- `o`, `O`
  
  - 移动到标记区域的末尾，移动到块的另一个角落

- `aw`
  
  - 标记一个单词

- `ab`, `aB`
  
  - 标记在(), {}内的块
  - `ib`, `iB`

- visual commands
  
  - `<`, `>`
    
    - 左右移动
  
  - `y`
    
    - 复制标记的文本
  
  - `d`
    
    - 删除标记文本
  
  - `～`
    
    - 大小写转换

- `ESC`
  
  - 退出visual mode

### Insert mode

- `i`, `I`
  
  - 进入插入模式
  - 在当前行首插入

- `o`/`O`
  
  - 在当前行的下/上一行插入

- `a`
  
  - 当前光标后加入

- `A`
  
  - 当前行的末尾加入

- `ea`
  
  - 当前词的末尾插入

- auto-completion
  
  - `C-N`, `C-P`
    
    - 自动补充下一个、上一个关键词
  
  - `C-X`,`C-F`
    
    - 自动补充文件名

### Replace mode

- `R`
  
  - 进入替换模式



---

## General

### yank/copy

- `n yy`
  
  - 复制n行

- `yw`
  
  - 复制当前单词

- `y$`
  
  - 从当前位置复制到行尾

### delete

- `x`
  
  - 删除字符

- `dd`
  
  - 删除行

- `D`, `d$`
  
  - 删除当前位置到行尾

- `d^`
  
  - 删除当前位置到行首第一个非空白位置

- `d0`
  
  - 删除当前位置到行首

- `dw`
  
  - 删除当前词

### modify

- 替换
  
  - `cc`, `C`
    
    - 替换整行
  
  - `cw`
    
    - 在下一个词的前面替换
  
  - `cb`
    
    - 在前一个词的开头替换
  
  - `c0`/`c$`
    
    - 在行首、行尾替换
  
  - `r`
    
    - 替换当前光标字符
  
  - `s`
    
    - 删除当前字符，并替换文本
  
  - `S`
    
    - 删除整行，并替换文本，等同cc

- `J`
  
  - 上下俩行合并

- `xp`
  
  - 交换当前俩个字符位置，等同先删除再粘贴

### paste

- `p`
  
  - 在光标后粘贴

- `P`
  
  - 在光标前粘贴

### indent

- `<, >`

### redo/undo

- `./u`
  
  - 重复上一个command, undo

- `C-r`
  
  - redo



---



## Windows

* `:vsp`, `:sp` : 纵向、横向分割窗口

* `:diffs` : 分割窗口并显示diff

* `C-wp` : 跳转到最近编辑过的窗口

* ` C-ww /wh ,wj, wk, wl` : 跳转窗口

* `C-ws` : 分割窗口

* `C-wv` : 纵向分割

* `C-wq` : 关闭窗口

## 

---



## Multiple files

* `:e file` : 在buffer中编辑文件

* `:bnext`, `:bn` : 转到下一个buffer

* `:bprev`, `:bp` : 转到下一个buffer

* `:bd` : 删除buffer，关闭文件

* `:ls` : 显示所有已打开的buffer

* `:sp`/`:vsp file` : 在一个新buffer中打开文件，并分割窗口

## 

---



## Tabs

* `:tabnew`, `:tabnew file `: 在新tab中打开文件

* `C-wT` : 将当前窗口文件移动到一个单独的tab显示

* `gt`, `:tabnext`, `:tabn` : 移动到下一个tab

* `gT`, `:tabprev`, `:tabp`: 移动到上一个tab

* `<number> gt` : 移动到第n个tab

* `:tabmove <number>` : 将当前tab移动到第n个位置

* `:tabclose`, `:tabc` : 关闭当前tab

* `:tabonly`, `:tabo` : 除当前tab外，关闭所有其他tabs

* `:tabo command` : 在所有tab中执行命令
  
  * 例： 关闭所有已经打开的tabs  `:tabo q` 







---

## Reference resources



1. https://github.com/wsdjeg/vim-galore-zh_cn

2. https://github.com/hackjutsu/vim-cheatsheet
