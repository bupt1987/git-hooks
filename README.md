Git Hooks
==================

依赖
=======

	composer require fp-coding-standards/fpcs

功能简述
========
1、在提交代码（git commit）到git库时，本钩子被触发。  
2、调用phpcbf和phpcs，来做代码检查并尝试自动修复代码样式。  
3、将修复后的代码提交到git库中。  


安装步骤
========

1、安装依赖PHP_CodeSniffer，定义代码样式，本例中使用[FunPlus-Coding-Standards](https://github.com/funplus/FunPlus-Coding-Standards)。  
2、安装钩子 ` vendor/bin/git-hooks-install`


参考
====

### 1. git钩子

参考 [Git Hook](http://githooks.com/) 或自行Google


### 2.代码检查

本钩子使用[PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)做代码检查，需要提前配置好PHP_CodeSniffer和PHP_CodeSniffer所需的rule set。


