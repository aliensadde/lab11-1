## Laboratory work XI

Данная лабораторная работа посвещена изучению инструментов отладки на примере **lldb**

```bash
$ open https://lldb.llvm.org/tutorial.html
```

## Tasks

- [ ] 1. Создать публичный репозиторий с названием **lab11** на сервисе **GitHub**
- [ ] 2. Выполнить инструкцию учебного материала
- [ ] 3. Ознакомиться со ссылками учебного материала
- [ ] 4. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
$ export GITHUB_USERNAME=<имя_пользователя>
```

```bash
$ git clone https://github.com/${GITHUB_USERNAME}/lab10 lab11
$ cd lab11
$ git remote remove origin
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab11
```

```bash
$ cmake -H. -B_build -DCMAKE_BUILD_TYPE=Debug -DCMAKE_INSTALL_PREFIX=_install
$ cmake --build _build --target install
$ cd _install/bin
```

```bash
$ lldb demo
(lldb) process launch --stop-at-entry
(lldb) breakpoint list
(lldb) breakpoint set --name print
(lldb) breakpoint set --file demo.cpp --line 12
(lldb) breakpoint list
(lldb) process launch
(lldb) exit
```

```bash
$ demo
<Command>-T
$ ps
$ lldb
(lldb) process attach --pid <идентификатор_процесса> 
(lldb) process attach --name demo
(lldb) exit
```

```bash
$ lldb demo
(lldb) process launch --stop-at-entry -- -program_arg "text1 text2 text3"
(lldb) thread list
(lldb) thread backtrace
(lldb) frame variable
(lldb) frame variable argv[0] 
```

```bash
$ lldb demo
(lldb) process launch --stop-at-entry
(lldb) thread continue
(lldb) thread step-in
(lldb) thread step-over
(lldb) thread step-out
(lldb) thread step-inst
(lldb) thread step-over-inst
(lldb) exit
```

```bash
$ sed -i '' 's/lab10/lab11/g' README.md
```

```bash
$ git add .
$ git commit -m"debugging"
$ git push origin master
```

## Report

```bash
$ cd ~/workspace/labs/
$ export LAB_NUMBER=11
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gistup -m"lab${LAB_NUMBER}"
```

## Links

- [gdb](https://www.gnu.org/software/gdb/)
- [lldb](https://lldb.llvm.org)
- [windbg](https://msdn.microsoft.com/en-us/library/windows/hardware/dn745911(v=vs.85).aspx)

```
Copyright (c) 2017 Vyacheslav Vershinin
```
