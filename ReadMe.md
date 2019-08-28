## What is this project?
This is Deeplearning2C. It's a project for generate an application for Android, Iphone, Linux, Windows and Mac OS X, that can generate a deep neural network in a .c file after being trained with Deeplearning4J.

I have been using the following dependencies

* Deeplearning4J
* GluonHQ JavaFX for Android & Iphone development
* Lombok
* Logback-classic

## Why should I use this application?
Let's say that you want to implement an deep neural network that are trained for classification for animals or other visible things. You want to implement it into a microcontroller such as STM32, PIC, AVR. Then this application can be used to generate a deep neural network in C code.

## How does it looks like?
Here are some images when I run Deeplearning2C on Linux.

Model selection

![a](https://raw.githubusercontent.com/DanielMartensson/Deeplearning2C/master/pictures/Models.png)

Menu

![a](https://raw.githubusercontent.com/DanielMartensson/Deeplearning2C/master/pictures/Menu.png)

Global configuration

![a](https://raw.githubusercontent.com/DanielMartensson/Deeplearning2C/master/pictures/Global.png)

Layer configuration

![a](https://raw.githubusercontent.com/DanielMartensson/Deeplearning2C/master/pictures/Layer.png)

Training data configuration

![a](https://raw.githubusercontent.com/DanielMartensson/Deeplearning2C/master/pictures/Data.png)

Training the model

![a](https://raw.githubusercontent.com/DanielMartensson/Deeplearning2C/master/pictures/Training.png)


Applied onto a Samsung Galaxy S3 from 2012

![a](https://raw.githubusercontent.com/DanielMartensson/Deeplearning2C/master/pictures/Samsung%20S3.jpeg)

## I like this project! How can I get the installation file?

First of all. The installation file is over 600 megabytes. That's huge, but anyway it's still possible to install. You need to have OpenJDK 8 and OpenJFX 8 installed. If you are an Ubuntu user, then follow these steps:

1. Install OpenJDK 8

```
sudo apt-get install openjdk-8-jdk
```

2. Install OpenJFX 8
```
Open sources.list file 

cd /etc/apt
sudo nano sources.list

Paste this into the file and save and close

deb http://de.archive.ubuntu.com/ubuntu/ bionic universe

Run these code inside the terminal

sudo apt-get update
sudo apt install openjfx=8u161-b12-1ubuntu2 libopenjfx-java=8u161-b12-1ubuntu2 libopenjfx-jni=8u161-b12-1ubuntu2 openjfx-source=8u161-b12-1ubuntu2
sudo apt-mark hold libopenjfx-java libopenjfx-jni openjfx openjfx-source
```

3. Install Eclipse 2018-09 (4.9.0) R (Because Eclipse 2018-09 will only work with Gluon Plugin 2.6.0)
```
  https://www.eclipse.org/downloads/packages/release/2018-09/r
```

4. Install Gluon Plugin 2.6.0 inside Eclipse
```
  Help -> Eclipse Marketplace -> Gluon 2.6.0
```

Now you can download my Deeplearning2C project and import that project into your Eclipse IDE.  Have fun and generate the .jar file for Win,Lin,Mac. 

5. (Optional) See the getting started guide for using GluonHQ JavaFX for mobile development. It's a very easy and excellent done graphical manual. It describes how to set up the Android SDK etc. https://docs.gluonhq.com/getting-started/#introduction

6. (Optional) Troubleshooting for Android can be done this way, if you got some issues with the application on the phone, but not on desktop. See selected answer https://stackoverflow.com/questions/42253794/androidinstall-task-causes-a-no-connected-devices-error

## What need to be working on?

* Make so C-code generation works. I have just getting header files to work.  Have a look at TrainEvalGeneratePresenter.java file 
* Generate an application for Iphone. Iphone app generation works, but I haven't tested it yet because I focusing on Android at the moment. 
* Search for bugs. If you find any...please open an issue or a pull request. 
* Scale down dependencies inside the build.gradle file, and only use the most necessary for training the deep neural network

## I want to add a layer and a updater! How can I do that?

After you have installed all the tools you need to create the installation files, such as .jar, .apk etc. you need to focus on these three java classes.

```
ConfigurationsPresenter.java <-- For configuration GUI
DL4JSerializableConfiguration.java <-- For creating the deep neural network
SimpleDependencyInjection.java <-- Class that make DL4JModel static and accessible for all classes
```

Those classes handle the configurations for both the GUI and file handling. Just read them and try to understand how I have made them. I allways use the same coding style for all classes and I try to make coding easy as possible so other users can understand my code. 

The idea behind Deeplearning2C is that I using Deeplearning4J and creates an interface for it. The configuration you making inside Deeplearning2C is more like a instructions how to create the deep neural network for Deeplearning4J. 

Please, use also SceneBuilder 8 from GluonHQ. An easy tool for creating or editing the *.fxml files inside the resources folder that are located inside the Deeplearning2C project.

## Tutorials - If you want to change inside the code
* Tutorials -> Add seed, regularization coefficient, learning rate, momentum
* Tutorials -> Add new updater
* Tutorials -> Add new layer
* Tutorials -> Add inputs and outputs
