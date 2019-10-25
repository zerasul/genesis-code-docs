# Commands

Genesis Code provides the next commands:

* Compile Project.
* Clean Project.
* Run Project.
* Compile & Run Project.
* Create Project.
* Set Gens Command path.

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

## Set Gens Command path

This command, allows you to configure the Gens Emulator Command in the Genesis Code Configuration. This command show a input box for set the Emulator Command.

**NOTE**: You can use others emulators like [Blastem](https://www.retrodev.com/blastem/).