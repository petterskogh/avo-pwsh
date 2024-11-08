# AvoShell

Avocado powered PowerShell setup. Inspired by [Hanselmans Ultimate PowerShell prompt](https://www.hanselman.com/blog/my-ultimate-powershell-prompt-with-oh-my-posh-and-the-windows-terminal?fbclid=IwAR0O6er7XgH5zY1oC6lCwK7ICjfqJvY8lTkvmwkAltPxeSFlyYEs23N3Y9E).

![Image of terminal with AvoShell setup](./AvoShellScreenshot.png)

## Features

📂 Open explorer on ctrl + click on path

📜 Display git repo status, including changed and stashed files

💁‍♀️ Display latest git commit

🔋 Display battery if low 

💽 Display RAM if high

👁️‍🗨️ Predictive autocomplete

## Install PowerShell

To get started install the .NET Core powered PowerShell from the [Microsoft Store](https://apps.microsoft.com/store/detail/powershell/9MZ1SNWT0N5D?hl=en-us&gl=us).

## Install and setup theme

When you have PowerShell installed, get Oh My Posh. This can be done easily by following their guide at [Oh My Posh Installation](https://ohmyposh.dev/docs/installation/windows). Use it to: 
* Install Oh My Posh
* Install [NerdFont](https://www.nerdfonts.com/font-downloads) (Includes icons needed)
* Configure your terminal to use font

To use the setup in this repo, add [theme.omp.json](./theme.omp.json) to the location pointed to by the environment variable POSH_THEMES_PATH (default path is C:\Users\\[user]\AppData\Local\Programs\oh-my-posh\themes). Add the following line to your PowerShell profile (open with VS Code: `code $PROFILE`).

```
oh-my-posh --init --shell pwsh --config "$env:POSH_THEMES_PATH\theme.omp.json" | Invoke-Expression
```

To edit the theme in VS Code, run the following line in your terminal.

```
code "$env:POSH_THEMES_PATH\theme.omp.json"
```

Update theme colors in your terminal to make it look sexy.

## Install and setup predictive autocomplete

To install autocomplete, run the following commands in PowerShell

```
Install-Module PSReadLine -AllowPrerelease -Force
Install-Module PowerType -AllowPrerelease
```

Then add the following lines to your PowerShell profile

```
Import-Module PSReadLine
Enable-PowerType
Set-PSReadLineOption -PredictionSource HistoryAndPlugin -PredictionViewStyle ListView
Set-PSReadLineOption -EditMode Windows
```

View [Profile.ps1](./Profile.ps1) for full profile
