# SVN

与其到处找免费的SVN图形化管理工具，还不如熟悉SVN常用的命令。

算了，太简单了，还是自己看吧：

```
$ svn help
usage: svn <subcommand> [options] [args]
Subversion command-line client, version 1.7.20.
Type 'svn help <subcommand>' for help on a specific subcommand.
Type 'svn --version' to see the program version and RA modules
  or 'svn --version --quiet' to see just the version number.

Most subcommands take file and/or directory arguments, recursing
on the directories.  If no arguments are supplied to such a
command, it recurses on the current directory (inclusive) by default.

Available subcommands:
   add
   blame (praise, annotate, ann)
   cat
   changelist (cl)
   checkout (co)
   cleanup
   commit (ci)
   copy (cp)
   delete (del, remove, rm)
   diff (di)
   export
   help (?, h)
   import
   info
   list (ls)
   lock
   log
   merge
   mergeinfo
   mkdir
   move (mv, rename, ren)
   patch
   propdel (pdel, pd)
   propedit (pedit, pe)
   propget (pget, pg)
   proplist (plist, pl)
   propset (pset, ps)
   relocate
   resolve
   resolved
   revert
   status (stat, st)
   switch (sw)
   unlock
   update (up)
   upgrade

Subversion is a tool for version control.
For additional information, see http://subversion.apache.org/
```

## SVN 版本合并

```
svn merge -r fromVersion:toVersion fromBencheLocalPath toBencheLocalPath
（如：svn merge -r 26546:HEAD /Users/tracy/Documents/SVN/BOC/branches/P301 /Users/tracy/Documents/SVN/BOC/branches/P302）
```

## 注意

SVN默认不会管理工程下面的静态库文件(.a)，修改配置如下：

```
open ~/.subversion/config
[auto-props]
global-ignores=.o .lo .la .al .libs .so .so.[0-9] .pyc .pyo .rej ~ ## .# ..swp .DS_Store .xcuserstate
```
