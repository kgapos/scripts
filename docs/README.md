# Scripts

![Scripts logo](images/scripts.png)

## Introduction

A collection of useful bash and PowerShell (pwsh) scripts.

## Table of Contents

- [Scripts](#scripts)
  - [Introduction](#introduction)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
    - [Usage](#usage)
    - [License](#license)
    - [Disclaimer](#disclaimer)

## Getting Started

### Prerequisites

You will need:
- [a PowerShell shell](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell) to run the scripts under `pwsh` directory.
- a bash shell to run the scripts under the `bash` directory.

### Installation

Windows:
- [Install PowerShell on Windows](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows) if necessary.
- Install WSL2 to run bash commands in Windows.

Linux: 
- [Install PowerShell on Linux.](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-linux)

MacOS:
- [Install PowerShell on MacOS.](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-macos)

### Usage

PowerShell:
- Load pwsh modules:
  ```pwsh
  Import-Module ./pwsh/HelloWorld.psm1 -DisableNameChecking
  ```
- Use pwsh functions, for example:
  ```pwsh
  Print-HelloWorld
  ```
- List modules with `Get-Module`
- Get help for a module with `Get-Help [module-name]`, e.g. `Get-Help HelloWorld`
- Run [pester unit tests](https://pester.dev/) with `Invoke-Pester`. This looks for tests recursively in the current working directory and its nested subdirectories.
- Create a function in [your powershell profile](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_profiles) for quick global access:
  ```pwsh
  function Test-Module {
    Invoke-Pester -Path "scripts\pwsh\Tests"
  }
  Set-Alias -Name "test"  -Value "Test-Module" -Scope Global
  Set-Alias -Name "t"     -Value "Test-Module" -Scope Global
  ```
  Then run with `t` or `test` from anywhere.

Bash:
- Use bash scripts, for example:
  ```bash
  ./bash/delete-workflow-runs.sh "kgapos/scripts"
  ```

### License

This project is licensed under [the MIT License](https://opensource.org/license/mit/), see [the LICENSE file](/LICENSE.md) for details.

### Disclaimer

These scripts are implemented in Windows and tested in WSL2 and Linux (Ubuntu 22.04). They should also work on macOS but are not tested there. Please raise issues if you find any.