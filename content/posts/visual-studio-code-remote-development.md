---
title: 'Visual Studio Code Remote Development'
date: Fri, 28 Feb 2020 23:32:01 +0000
draft: false
tags: ['Dev machine', 'Dev tools']
---

**Visual Studio Code Remote Development** allows you to use a container, remote machine, or the [Windows Subsystem for Linux (WSL)](https://docs.microsoft.com/windows/wsl?WT.mc_id=-blog-scottha) as a full-featured development environment. It effectively splits VS Code in half and runs the client part on your machine and the "VS Code Server" basically anywhere else. The [Remote Development extension pack](https://aka.ms/vscode-remote/download/extension) includes three extensions. See the following articles to get started with each of them:

* [Remote - SSH](https://code.visualstudio.com/docs/remote/ssh?WT.mc_id=-blog-scottha) - Connect to any location by opening folders on a remote machine/VM using SSH.
* [Remote - Containers](https://code.visualstudio.com/docs/remote/containers?WT.mc_id=-blog-scottha) - Work with a sandboxed toolchain or container-based application inside (or mounted into) a container.
* [Remote - WSL](https://code.visualstudio.com/docs/remote/wsl?WT.mc_id=-blog-scottha) - Get a Linux-powered development experience in the Windows Subsystem for Linux.

Lemme give a concrete example. Let's say I want to do some work in any of these languages, except I don't have ANY of these languages/SDKS/tools on my machine.

**Aside:** You might, at this point, have already decided that I'm overreacting and this post is nonsense. Here's the thing though when it comes to remote development. Hang in there.

On the Windows side, lots of folks creating Windows VMs in someone's cloud and then they RDP (Remote Desktop) into that machine and push pixels around, letting the VM do all the work while you remote the screen. On the Linux side, lots of folks create Linux VMs or containers and then SSH into them with their favorite terminal, run vim and tmux or whatever, and then they push text around, letting the VM do all the work while you remote the screen. In both these scenarios you're not really client/server, you're terminal/server or thin client/server. VS Code is a thick client with clean, clear interfaces to language services that have location transparency.

...

Please continue with the source of this article on Hanelmann's blog [here](https://www.hanselman.com/blog/VisualStudioCodeRemoteDevelopmentMayChangeEverything.aspx).
