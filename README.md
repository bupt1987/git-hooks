pre-commit hook
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
假设目录结构：

    YOUR_PROJECT_ROOT/
      |—— git_hook
      		|—— pre-commit
      		|——ruleset.xml
      		|—— vendor/
           		|——bin/
                	|——phpcs
                	|——phpcbf

1、安装依赖PHP_CodeSniffer，定义代码样式，本例中使用[FunPlus-Coding-Standards](https://github.com/funplus/FunPlus-Coding-Standards)。  
2、git中注册钩子。

    cd YOUR_PROJECT_ROOT/.git/hook/
    ln -s ../../git_hook/pre-commit .



钩子的配置参考
==============
环境相关

    define('PROJECT_ROOT', YOUR_PROJECT_ROOT); //项目的路径
    define('PHP_CS_CHECK_CMD', PROJECT_ROOT.'/vendor/bin/phpcs'); //执行检查的命令
    define('PHP_CS_FIX_CMD', PROJECT_ROOT.'/vendor/bin/phpcbf'); //修复的命令
    define('PHP_CS_RULESET', __DIR__.'/ruleset.xml'); //检查和修复使用的rule set，可以为""
流程相关

    define('AUTO_FIX_CS', TRUE);    //是否自动修复文件

参考
====

### 1. git钩子

参考 [Git Hook](http://githooks.com/) 或自行Google


### 2.代码检查

本钩子使用[PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)做代码检查，需要提前配置好PHP_CodeSniffer和PHP_CodeSniffer所需的rule set。


