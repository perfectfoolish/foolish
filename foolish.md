# Reference video and notes ( 参考笔记 ) 

http://billie66.github.com/index.html

https://github.com/happypeter

https://github.com/wanggege

http://happypeter.org 

# Network Application

ifconfig                View IP addresses

sudo dhclient eth1      Connect to the Internet

sudo pppoeconf          Dialup Internet Connection

## SSH Login ( moreover ftp http )

  Client default install ssh-client  at the same time   Server : sudo apt-get install openssh-server (Installation Complete,Port automatically open)

eg: 
    
    ssh peter@192.168.1.17

    enter the password of peter

    return Client (ctrl-d or exit)

    scp (-r) peter@192.168.1.17:~/hihihi .   (-r use for dir)

    sudo service ssh stop 

    sudo service ssh start

    sudo !!

    service ssh status

## rsync


     
# C

http://tldp.org/HOWTO/Program-Library-HOWTO/

http://jonas.nitro.dk/tig/

hen of Peter

    echo  use printing value

    make  执行成功的前提是当前文件夹中有makefile文件



# vim

## video

http://www.derekwyatt.org/vim/vim-tutorial-videos/vim-novice-tutorial-videos/

    vim 以UTF8的字符编码方式写的
         
    lsb_release -a       examine system information

   * 要粘贴必须进入插入模式,否则格式乱了

    Command = operator + number + motion

                d(elete)  1,2

                y(ank)             gg+G

## 删除类命令d的格式如下(Normal)：

        [number]  command  object    or     command   [number]    object
   
        dw 从当前光标当前位置直到单字/单词末尾，包括空格

        de 从当前光标当前位置直到单字/单词末尾，但是不包括空格
                                                  
        d$ 从当前光标当前位置直到当前行末尾
        
        dd 删除光标所在的整行 

## 撤消类命令

        u  撤消最后执行的命令

        U  撤消在一行中所做的改动即修正整行
  
        CTRL R 执行恢复命令，即撤消掉以前的撤消命令，也就是恢复以前的操作结果

## 其他类命令

        Shift ctrl t 打开新的bash

        ctrl PgUp  or  ctrl PgDn  切换打开的多个bash

        ctrl-n  In insert mode,use to complement all the string,当前文件的内容和头文件的内容

        i_ctrl-x-f     补齐路径

        i_ctrl-x-k     

        shift-zz  
         
        Esc-:wq   quit after save

        file filename or dir  view properties of file and dir

        :number   光标快速跳转到此行

## open another bash in vim

1.先保存文件 :w

2.open bash :sh

3.close bash = ctrl d

4.退出vim  :q

 这种情况下可不关闭vim的情况下编译源程序，方便源程序的修改



## multiple files

    :ls   see buffers

    :bn   go to next buffer

    :bp   go to previous buffer

    :bd   delete a buffer


## VISUAL LINE

        Shift v   enter VISUAL LINE  [d(elete)  p(aste) ] PgUp PgDn to select    
        Shift v   exit  VISUAL LINE
         
        整体缩进几行代码:
                        
            首先用可视行模式选中这几行，然后 >  or  <

##the reason why .swap file appearing

1. open the same file twice sametime

2. close the file unnormal

## Configuration files

## .vimrc

home下的创建本机的.vimrc（隐藏文件）文件，该文件是vim的配置文件

map 用来将指令映射成简单操作或设置自己想要的快捷键

map ,ss :set spell<cr>   key map 单词拼写检查

map <tab> :bn<cr>        切换同时打开的多个buffer

imap JJ <esc>

imap jj <esc>            从插入模式退出到普通模式

set hidden               隐藏：bn转换的报错信息

set autoindent           设置自动缩进

set expandtab            设置`<Tab>`的作用 展开成空格

set tabstop=4            设置`<Tab>`的作用 展开成4个空格

set shiftwidth=4         shift-v + > 时候展开成空格的个数

set dictionary=/usr/share/dict/words    添加系统自带的字典

## .bashrc



## .gitconfig



# plugin 

(安装vim插件的实质：用命令行把插件安装在home下的.vim中，即~/.vim)
 
## snipmate

http://www.vim.org/scripts/script.php?script_id=2540

http://code.google.com/p/snipmate/issues/list

http://github.com/msanders/snipmate.vim
   
http://www.vimer.cn/2010/04/vimgvim%E4%B8%AD%E5%AF%B9snipmate%E7%9A%84%E5%B0%8F%E5%A6%99%E7%94%A8.html
 
cd .vim

cd snippets

vim c.snippets

# markdown

http://happypeter.github.com/LGCB/book/toy_markdown.html

## about markdown

   markdown文本书写时一定要注意在内容行缩进和与标题之间的空行

# markdown using

## download and install markdown

   1.sudo apt-get install markdown

## creat my .md directory

   2.vim my_note.md

##change .md to .html

   3.markdown my_note.md > my_note.html

## open .html directory

   4.firefox my_note.html&

## html study

http://www.w3schools.com/


# github

login my own github in github website   

https://github.com

http://www.happypeter.org/posts/21
# git

## install

    sudo apt-get install git-core
    
    sudo apt-get install tig

    sudo apt-get install gource        跳转到一个项目内运行gource   

##clone others respository

   git clone + 链接(end with .tg)

   git pull

## git basics

## Global setup: 全局配置 强烈要求要做  规范操作

  Set up git

  git config --global user.name "lifulei"  

  git config --global user.email az00000000@126.com
        
Next steps:

1. first create a dir

        mkdir ggg

2. now you MUST cd to this dir

        cd ggg

3. initializing this git dir

        git init

    now you can see a `.git` in this dir

        ls -a

4. now create a file

        vim hello.c

5. let git knows about this file

        git add hello.c

6. create the first version

        git commit -a -m "my first commit"   //-a跟踪所有修改-m修改信息，说明性内容，说明为什么修改等

7. 上传新版本到仓库

        git remote add origin git@github.com:perfectfoolish/foolish.git  添加远端远端>门牌号,给链接起别名

        git push -u origin master        master是仓库的以部分

8.每次修改完都要重复执行6


9.Existing Git Repo

  cd existing_git_repo

  git remote add origin git@github.com:perfectfoolish/foolish.git

  git push -u origin master

## ref

http://progit.org/

video: search "linus git" at youku.com

# linux basics

Linux is OS(operating system)

OS as linus see it:

OS is nothing but the kernel.

Linux is nothing but the kernel.

ubuntu is Linux + 1000 app.

OS as MS see it:

OS is kernel + desktop env.

# tips

   date

   Clear screen : Ctrl-l

   Copy and Paste: select -> middle button

## language

https://github.com/happypeter/job-akae/wiki

## translation

http://dict.youdao.com/

# shell ( shell is a commandline interpreter )

bash is a kind of shell.

## Where are you ?

   which ls

   locate vimrc
   sudo updatedb   update locate

   find xxx|grep git

   ps aux | grep firefox  (找出Firefox的进程)

   kill 2003   (2003代表进程号)

   kill -9 2003  (强行关闭进程)

find a string in a project

https://github.com/happypeter/hen/blob/master/search/curse/xxx.c

## filesystem tree

    ls

    cd      ~ means your home dir

    cd ..   go to the parent of current dir

    pwd

    man pwd     q to quit

    mkdir dir

    cp   copy file
    
    cp -r directory   递归复制目录

### path

    绝对路径: start with /

    相对路径: start with .

## shell prompt

    peter@cow:~/tg-note$

    user@machinename:currentWorkingDirectory(folder)$

# software installation

    sudo apt-get install tree

# tar 

http://www.happypeter.org/posts/10

# ref

http://happypeter.github.com/LGCB/

http://billie66.github.com/TLCL/book/

# reading

http://norvig.com/21-days.html

## some of my favorite sites

http://www.linfo.org/

http://www.wikipedia.org/

http://news.ycombinator.com/news

# Ruby on Rails Tutorial second edition

## set up development environment

### install Ruby, RubyGems, Rails, Git 

$ rvm get head && rvm reload  # update and reload RVM

$ rvm install 1.9.3

$ rvm use 1.9.3@railstutorial2ndEd --create --default

$ rvm --help

$ rvm gemset --help

$ gem update --system 1.8.24

vim ~/.gemrc
  
     install: --no-rdoc --no-ri

     update: --no-rdoc --no-ri

$ gem install rails -v 3.2.12

lifulei@cow:~/Books/first_app$ bundle install

Fetching gem metadata from https://rubygems.org/...........

Fetching gem metadata from https://rubygems.org/..

Bundler could not find compatible versions for gem "activesupport":

  In snapshot (Gemfile.lock):

    activesupport (3.2.8)

  In Gemfile:

    rails (= 3.2.12) ruby depends on

      activesupport (= 3.2.12) ruby

Running `bundle update` will rebuild your snapshot from scratch, using only

the gems in your Gemfile, which may resolve the conflict.

















