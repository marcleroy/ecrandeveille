---
title: 'Powershell configuration in Windows Terminal'
date: 2023-11-28T15:30:42+01:00
tags: ['Dev machine','Terminal']
draft: false
---

Configuring the Windows Terminal prompt with Oh-My-Posh involves a few steps. 
Here's a general guide:

### Install Windows Terminal
If you haven't installed Windows Terminal, you can download it from the Microsoft Store or from the GitHub releases page: [Windows Terminal Releases](https://github.com/microsoft/terminal/releases).

### Install PowerShell Core
Oh-My-Posh works best with PowerShell Core. You can download and install it from the official GitHub releases page: [PowerShell GitHub Releases](https://github.com/PowerShell/PowerShell/releases).

### Install Oh-My-Posh
Open a PowerShell terminal and run the following command to install Oh-My-Posh:

~~~powershell
Install-Module -Name oh-my-posh -Scope CurrentUser
~~~

### Install a Powerline Font
Oh-My-Posh often requires a font with Powerline symbols. You can download and install one of the recommended fonts from the Nerd Fonts project.

Configure PowerShell Profile:
Open your PowerShell profile by running:

~~~powershell
code $PROFILE
~~~

Add the following lines at the end of your profile to import Oh-My-Posh and set the theme:

~~~powershell
Import-Module oh-my-posh
Set-PoshPrompt -Theme <your_theme_name>
~~~

Replace <your_theme_name> with the name of the theme you want to use. You can find available themes by running Get-PoshThemes.

Configure Windows Terminal:
Open your Windows Terminal settings (press Ctrl + ,), and add the following to the "profiles" array:

~~~json
"fontFace": "Your Chosen Nerd Font",
"fontSize": 12,
"startingDirectory": "//wsl$/Ubuntu-20.04/home/your_username",  // Adjust this for your setup
"useAcrylic": true,
"acrylicOpacity": 0.8,
"colorScheme": "One Half Dark",  // Choose a color scheme you like
"cursorShape": "filledBox",
~~~

Adjust the values based on your preferences and system configuration.

Restart Your Terminal:
Close and reopen Windows Terminal to apply the changes.

That's it! Your Windows Terminal should now display the Oh-My-Posh prompt with the configured theme. Adjustments may be needed based on your preferences and system setup.

### Installing posh-git

Installing posh-git is a good idea, especially if you're using Git. posh-git integrates with Oh-My-Posh to provide additional Git-related information in your prompt.

Here are the steps to install posh-git:

Open a PowerShell terminal and run the following command to install posh-git:

~~~powershell
Install-Module -Name posh-git -Scope CurrentUser
~~~
Add the following lines to your PowerShell profile (usually located at $PROFILE):

~~~powershell
Import-Module posh-git
~~~
If you want to customize the appearance of Git-related information in your prompt, you can also set the prompt colors. For example:

~~~powershell
$GitPromptSettings.DefaultPromptBeforeSuffix.Text = "`e[96m" # Changes the color to light cyan
~~~

Feel free to adjust the colors based on your preferences.
Save the profile, and then restart your PowerShell session or open a new Windows Terminal instance.

With posh-git installed and integrated, you should now see Git-related information, such as the current branch, status, and more, in your Oh-My-Posh prompt.

### References and links

 - [Installation of Windows Terminal themes](https://windowsterminalthemes.dev/)

 - [Make Windows Terminal Look Better | Oh My Posh Guide](https://www.youtube.com/watch?v=-G6GbXGo4wo)

 - [Oh My Posh - A prompt theme engine for any shell.](https://ohmyposh.dev/)

 - [Oh My Posh - Themes](https://ohmyposh.dev/docs/themes) 

 - [Nerd fonts](https://github.com/ryanoasis/nerd-fonts/releases)

 - [GitHub of posh-git](https://github.com/dahlbyk/posh-git)






