# Commands

Genesis Code provides the next commands:

* Compile Project.
* Clean Project.
* Run Project.
* Compile & Run Project.
* Create Project.
* Set Gens Command path.
* Compile for Debugging.
* Import a new TMX file.
* Import a new Json TMX file.

**NOTE**: All the commands start with "Genesis Code: ".

## Compile Project

This command, allow to compile the project using the SGDK makefile. With this command the resources are procesed too (images, sprites, music,...). Its important to set the GDK/GDK_WIN or the GENDEV enviroment variables.

## Clean Project

This command, allows you to clean the project using the SGDK makefile. This command will remove the _rom.bin_ file and some generated files. See SGDK project for more information.

## Run Project

This command, allows you to run the rom generated binary with an Emulator. Its open the emulator with the current rom.bin file that is inside the out folder of the current project.

**NOTE**: You need to configure the Gens Emulator command path in the Genesis Code Configuration.

## Compile & Run Project

This command, first compile the project and later run the generated _rom.bin_ file with the current emulator.

**NOTE**: You need to configure the Emulator command path in the Genesis Code Configuration.

## Create Project

This command, allows you to create a new project for use with SGDK or GENDEV. This command, first, allow you to select the folder where the project will be created. Later, will be create three folders (src, inc and res); and initialize a git repository with the .gitignore file. For last, a hello world example will be created.

From v1.5.1 of Genesis Code when a new Project is created the C/C++ settings configuration is created using the current configuration values instead using System Environment variables(using the variables configuration of current Toolchain). If there is no value for the current configuration, the System Environment variable value is used.

### MarsDev

If you create the project with the MarsDev toolchain selected in the genesis code Settings, the project is created for use with this toolchain adding a MakeFile and all the files needed for use it with MarsDev.

### Debugging

If you create a new project, it create an ```.vscode``` folder that contains the file ```launch.json```  the debugging configuration for use GDB for remote debugging.

## Set Gens Command path

This command, allows you to configure the Gens Emulator Command in the Genesis Code Configuration. This command show a input box for set the Emulator Command.

**NOTE**: You can use others emulators like [Blastem](https://www.retrodev.com/blastem/).

## Compile For Debugging

This command, compile the project with the debug options. This command, change if the toolchain selected in settings is SGDK/GENDEV or MARSDEV.

**NOTE:** Due to problems with [GENDEV](https://github.com/kubilus1/gendev) project; dosen't have the libmd.a lib with the debug options, you can't use this command on Linux Systems.

## Import TMX file

This command, allows you to create a header C File (.h) from a TMX (XML) format file.

## Import Json TMX File

This command, allows you to create a header C file (.h) from a TMX Json (.json) format file.
