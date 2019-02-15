# _tkinter
this article introduce how to solve the problem"ImportError: No module named _tkinter"

When we use "import Tkinter" in python2.7+ or use "import tkinter" in python 3.0+,most people could meet this problem "ImportError: No module named _tkinter",But how to solve?

## First: Install  Tkinter

In console,we can use this command:
  sudo apt-get install python-tk         //if you use python2.7+
Or 
  sudo apt-get install python3-tk        //if you use python3.0+
  
## Then: Install tcl and tk

DownloadAddress:http://www.tcl.tk/software/tcltk/download.html

 download package: tcl8.7a1-src.tar.gz  &  tk8.7a1-src.tar.gz
 
    (1) install tcl8.7a1-src.tar.gz：   
           $:tar -xzvf tcl8.6.1-src.tar.gz
           $:cd tcl8.7a1/unix/
           $:./configure
           $:make
           $:sudo make install
           
    (2) install tk8.7a1-src.tar.gz：
           $:tar -xzvf tk8.7a1-src.tar.gz
           $:cd tk8.7a1/unix/
           $:./configure
           $:make
           $:sudo make install
      when you make you would meet this mistake:"No such file or directory",you can do this to sure you install success:
           $:sudo apt-get install libx11-dev
           $:sudo make install
      when you use 
           $:wish  
           $:info tclversion  
      you can see the tk_version,and then you neet install the general lib 
           $:sudo apt-get install autoconf curl libmysqld-dev libaio-dev libjpeg62-dev libpng12-dev libfreetype6-dev libssl-dev zlib1g-dev
           $:sudo apt-get install  libbz2-dev libgdbm-dev  
           $:sudo apt-get install sqlite3 libsqlite3-tcl libsqlite3-dev  
           $:sudo apt-get install  python-bsddb3  
           
       (3) Sure your python can use "import tkinter":
           $:python
           $:import Tkinter(this command only used in python 2.7+,if your python version latter than python3.0,you need use "import tkinter"
        if the console No pop-up message，it means you install _tkinter successful,while the console Appear Popup Message，
        you can run command again:
           $:sudo apt-get install python-tk
