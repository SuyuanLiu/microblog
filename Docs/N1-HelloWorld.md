# Chapter 1: Hello World

环境：mac

不同的 application 可能会用到不同版本的安装包，为了解决这个问题，在每个 application 中，使用虚拟环境，安装对应版本的安装包，这样使得不同 application 的安装包互不影响。

`mkdir microblog`,  
`cd microblog`, 创建文件夹 microblog 并进入.

`python3 -m venv venv`, 创建虚拟环境（python3.4 以上版本直接使用此命令），此时 microblog 文件夹下出现一个 venv 的文件夹。

`source venv/bin/activate`，启动虚拟环境，终端命令行前面出现 `(venv)`

`pip install flask`，安装 flask

code...写代码

`export FLASK_APP=microblog.py`，设置 FLASK_APP 变量，  
`flask run`, 运行程序

`pip install python-dotenv`，每次运行程序前设置 FLASK_APP 变量太麻烦，安装 python-dotenv，在 microblog 文件夹下建一个`.flaskenv`文件，里面写入`FLASK_APP=microblog.py`，之后都会自动 import FLASK_APP 变量。
