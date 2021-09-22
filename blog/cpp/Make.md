# GNU Make

GNU Make 是一个从程序源文件控制程序可执行文件和其他非源文件的生成的工具。

Make从一个叫makefile的文件中获取如何去build你的程序，makefile列举了每一个非源文件和如何从其他文件里引用这些文件。如果你写了一个程序，你应该为它编写makefile，以便来用Make去build或install该程序。

### Make的能力

+ Make能让最终用户在不知道处理细节的情况下build和安装你的package，因为这些细节被记录在你提供的makefile中了
+ Make根据哪些文件被修改自动计算出哪些文件需要更新；如果某个非源文件依赖于另一个非源文件，Make也将自动决定适当的更新文件顺序。
  因此，如果你只改变少数几个源文件，然后执行Make，就无需重编译整个程序，仅仅会更新那些你更改的源文件所直接或间接依赖的非源文件。
+ Make没有限制任何特定语言。对程序中的每个非源文件，makefile制定shell命令去处理它们。
+ Make不限于build一个package。
### Make的rules和targets
Make中的rule告诉Make为了从源文件构建target文件要如何去执行一系列的命令。Make中也可以指定target文件的依赖列表，该列表应该包含rule中被用作输入到命令的所有文件（无论是源文件还是其他的targets）。
这里是一个rule的简单例子：

```makefile
target:	dependences ...
				commands
				...
```

当你运行Make时，你可以指定要更新的特定的target，否则，Make将更新makefile中的第一个target，当然为了生成这些target作为输入的其他任意target一定会被首先更新。