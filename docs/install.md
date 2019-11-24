# Installation

 You can find Genesis Code in the [Microsoft Marketplace for Extensions](https://marketplace.visualstudio.com/items?itemName=zerasul.genesis-code); when you find the extension click on install via web or via visual studio code.

 You also, can install via our release tags on the [Github Repository](https://github.com/zerasul/genesis-code) of Genesis Code and install using [visual studio code Extension Instalation Command](https://vscode-docs.readthedocs.io/en/stable/extensions/install-extension/).

## Configuration

 To use Genesis code, you need to configure two important things.

 First, you need to install and configure your Genesis Development Kit; it can be SGDK or GENDEV projects.

 Its important to set the enviroment variable of GDK for SGDK projects, or GENDEV enviroment variable for GENDEV based project.

```bash
set %GDK%=f:/sgdk
```

```bash
export GENDEV=/opt/gendev
```



For more information you can see the repositories of [SGDK](https://github.com/Stephane-D/SGDK) or [GENDEV](https://github.com/kubilus1/gendev).

After configure the SGDK or GENDEV enviroment, we need to configure the Gens path command.

### Configuration in MaCOs (since v1.1.0).

To use SGDK and Genesis code in MacOs, you need to install and configure Wine for use with SGDK. Follow the next instructions for install and configure SGDK with Wine in MacOs.

1 . Install [brew](https://brew.sh/index) on your system.
2 . Create and configure the installation directory:

```bash
sudo mkdir /opt/gendev/
sudo chown $USER: /opt/gendev
```
3 . Set the next environment Variables.

```bash
export GENDEV=/opt/gendev
export GDK='c:/sgdk'
export GDK_WIN='c:\sgdk'
```

**NOTE**: Remember to put this variables into your bash_profile to make them permanent.

4 . Install the packages needed with _brew_.

```bash
brew cask install xquartz
brew install wine
```

5 . Configure wine

```bash
mkdir $GENDEV/wine
WINDEBUG=-all WINEARCH=win32 WINEPREFIX=$GENDEV/wine wineboot
```

6 . clone SGDK project using git.

```bash
cd $GENDEV
git clone https://github.com/Stephane-D/SGDK.git
ln -sv $GENDEV/SGDK $GENDEV/wine/drive_c sgdk
```

7 . For use Java with SGDK for the resource management you need to install Java in the wine system. First, you need to dowload the JDK (using oracle or openjdk); its important to download the x86 version (32 bits). Once downloaded we need to install it in wine.

```bash
cd <your folder where the jdk installer is downloaded>
WINEPREFIX=$GENDEV/wine wine cmd
```
```bash
z:\> jdk-8u221-windows-i586.exe /s
```

8 . Once java is instaled in wine, we need to configure the wine environment variables to add java to the Path variable.

```bash
WINEPREFIX=$GENDEV/wine wine regedit
```

This will open the register editor in wine; now we need to go the the next register path: ```HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Session Manager\Environment```; and change the PATH variable adding the current windows java path.

9 . For last, we need to compile and build all the tools in SGDK.

```bash
WINEPREFIX=$GENDEV/wine wine cmd
%GDK_WIN%\bin\make -f %GDK_WIN%\makelin.gen
```

**NOTE:** thanks to the [https://github.com/v4ld3r5/sgdk_vscode_template.git](https://github.com/v4ld3r5/sgdk_vscode_template.git) project for this configuration.

### Gens Path Command Configuration

To use an Emulator like [Gens](http://gens.me/) you need to configure your gens path Command Configuration.

This configuration store you gens command to call the emulator and open the attached rom binary. In this case you can set it by tow ways.

The first way is using the Genesis Code Configuration. You can see the settings section in your visual studio instalation using the menu File->preferences->settings (or with the ctrl+, shortcut).

![Genesiscodeconfiguration](img/genscodesettings.png)

The second way is using the Set run path Command; this command allows you to put the Gens Emulator command in one Input Box. For more information, please see commands section.