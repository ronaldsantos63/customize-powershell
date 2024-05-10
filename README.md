# Personalizar windows terminal

Personalização do windows terminal

## Ferramentas

- [chocolatey](https://chocolatey.org/)
- [Scoop](https://scoop.sh/)
- [Git](https://git-scm.com/download/win)
- [oh-my-posh](https://ohmyposh.dev/docs/installation/windows)
  - [PSReadline](https://github.com/PowerShell/PSReadLine)
  - Cascadia Nerd Font
  - Terminal Icons
  - Posh-Git

## Instalando ferramentas

### Instalando chocolatey

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

### Habilitar execução de scripts no powershell (Executar como administrador)

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
```

### Instalar Scoop

```powershell
iwr -useb get.scoop.sh | iex
```

### Instalar Git Windows

```powershell
winget install --id Git.Git -e --source winget
```

### Instalar Oh My Posh

Instalar OhMyPosh

```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
```

Instalar PSReadline

Para Powershell 7

```powershell
Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
```

Para versões anteriores do powershell

```powershell
Install-Module -Name PSReadLine -Scope CurrentUser -Force -SkipPublisherCheck
```

Instalar Cascadia Fonts

```powershell
oh-my-posh font install
```

Instalar Terminal Icons

```powershell
Install-Module -Name Terminal-Icons -Repository PSGallery -Scope CurrentUser
```

Instalar Posh-Git

```powershell
Install-Module posh-git -Scope CurrentUser
```

## Configurando tudo

### Configurando Windows Terminal

1.  Abrir pasta LocalState

        %LOCALAPPDATA%\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState

1.  Copiar todos os arquivos da pasta LocalState

### Configurando Profile

1. Abrir powershell no Windows Terminal
2. Criar arquivo Profile, apenas se não existir

```powershell
New-Item -Path $PROFILE -Type File -Force
```

3. Copiar todo o contéudo do arquivo Profile/profile.ps1 para o arquivo $PROFILE
