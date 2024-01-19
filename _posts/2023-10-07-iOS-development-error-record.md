---
layout: post
title: iOS development debuging error record
date: 2023-10-07 16:40:16
description: Here is the iOS development debuging error record.
tags: iOS Programming Error
categories: posts
giscus_comments: true
related_posts: true
---


## pod init error

```
$ pod init
Ignoring ffi-1.15.5 because its extensions are not built. Try: gem pristine ffi --version 1.15.5
xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance
/usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/cocoapods-1.11.2/lib/cocoapods/user_interface/error_report.rb:34:in `force_encoding': can't modify frozen String (FrozenError)
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/cocoapods-1.11.2/lib/cocoapods/user_interface/error_report.rb:34:in `report'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/cocoapods-1.11.2/lib/cocoapods/command.rb:66:in `report_error'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/claide-1.1.0/lib/claide/command.rb:396:in `handle_exception'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/claide-1.1.0/lib/claide/command.rb:337:in `rescue in run'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/claide-1.1.0/lib/claide/command.rb:324:in `run'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/cocoapods-1.11.2/lib/cocoapods/command.rb:52:in `run'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/cocoapods-1.11.2/bin/pod:55:in `<top (required)>'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/bin/pod:23:in `load'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/bin/pod:23:in `<main>'
/usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/xcodeproj-1.21.0/lib/xcodeproj/project.rb:228:in `initialize_from_file': [Xcodeproj] Unknown object version (56). (RuntimeError)
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/xcodeproj-1.21.0/lib/xcodeproj/project.rb:113:in `open'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/cocoapods-1.11.2/lib/cocoapods/command/init.rb:41:in `validate!'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/claide-1.1.0/lib/claide/command.rb:333:in `run'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/cocoapods-1.11.2/lib/cocoapods/command.rb:52:in `run'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/gems/cocoapods-1.11.2/bin/pod:55:in `<top (required)>'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/bin/pod:23:in `load'
	from /usr/local/Cellar/cocoapods/1.11.2_2/libexec/bin/pod:23:in `<main>'
```



1. **更新Homebrew本身**：
    ```bash
    brew update
    ```

2. **升级已安装的formulae**：
    ```bash
    brew upgrade
    ```

3. **清理旧的版本**（可选，但推荐）：
    ```bash
    brew cleanup
    ```

这三个步骤将确保你的Homebrew安装和所有安装的包都是最新的。
如果你不确定Homebrew是否需要更新，可以运行 `brew outdated` 来查看那些已安装的formulae有可用的更新。
如果你在加拿大或其他国家/地区，并希望切换回Homebrew的默认源，可以按照以下步骤操作：

### 1. 切换Homebrew的核心源回到官方源:

进入Homebrew的repository目录并重置远程URL为官方源。

```bash
cd "$(brew --repo)"
git remote set-url origin https://github.com/Homebrew/brew.git
```

### 2. 切换Homebrew Bottles的源回到官方源:

你需要从你的shell配置文件中移除或注释掉之前设置的 `HOMEBREW_BOTTLE_DOMAIN`。

- 对于bash用户，编辑 `~/.bash_profile` 或 `~/.bashrc` 文件，找到类似下面的行：

    ```bash
    export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles
    ```

    将其删除或注释掉。

- 对于zsh用户，编辑 `~/.zshrc` 文件，找到类似的行并删除或注释掉。

删除或注释之后，保存文件并重新加载你的shell配置：

```bash
source ~/.bash_profile   # 对于bash
# 或
source ~/.zshrc         # 对于zsh
```

完成上述操作后，Homebrew将使用其默认源下载和更新内容。