# notpad++windows版在安装NPPEXEC插件之后，按f6可以编写脚本，下面构造代码编译
### JAVABUILD（用来编译并运行单个java文件）
> 路径为src路径放源代码，out路径存放编译好的执行文件

```sh
NPP_SAVE
cd $(CURRENT_DIRECTORY)
C:\Program Files\Java\jdk1.8.0_91\bin\javac -d ..\out  $(FILE_NAME)
cd  $(CURRENT_DIRECTORY)\..\out\
java $(NAME_PART)
```
### gcc （用来编译并运行单个c语言文件）
> gcc编译c代码，前提是配置了path环境变量，否则需要用编译器完整路径，默认编译到相同路径 

```sh
cd "$(CURRENT_DIRECTORY)"  
gcc  $(FILE_NAME) -o $(NAME_PART).exe
$(NAME_PART).exe
```
### l2p_project（用来编译LaTex）
> latex编译，文件路径设置和JAVABUILD一致

```sh
NPP_SAVE
C:\FreeOfInstall\app\l2p.bat   "$(CURRENT_DIRECTORY)"  "$(CURRENT_DIRECTORY)\$(NAME_PART)"  "$(NAME_PART).pdf"
```
* 上面的l2p.bat批处理文件
```bat
::NPP_SAVE
::cd "$(CURRENT_DIRECTORY)"  
::C:\FreeOfInstall\app\miktex_to_latex.bat  "$(CURRENT_DIRECTORY)"  "$(NAME_PART)"  "$(NAME_PART).pdf"
::
::
::
::
@echo off
%~d1  
cd %1.\..\out
pdflatex %2
del *.dvi 
del *.out 
del *.log  
del *.aux   
del *.bbl     
del *.blg   
del *.brf   
del *.toc 
START "" "C:\FreeOfInstall\app\SumatraPDF.exe" "%3" -reuse-instance 
goto:eof 
```


