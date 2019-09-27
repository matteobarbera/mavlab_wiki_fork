= SmartUAV Installation =
This page describes how to checkout the svn repository for SmartUAV and compile for the first time on Windows and Linux.

== Linux ==

SmartUAV is stored on an svn server. To get a local copy on your pc, in a terminal, navigate to the file location you want SmartUAV and execute the following command. go 
{{{
sudo apt-get install svn
cd $local folder location where you want SmartUAV parent folder installed$
svn checkout https://svn.lr.tudelft.nl/MAVLAB/SmartUAV/
}}}

Several libraries are needed to build the minimal version on SmartUAV, to install these all, type the following into a terminal:
{{{
sudo apt-get install build-essential libgl1-mesa-dev libglu1-mesa-dev libsdl1.2-dev libxft-dev libxinerama-dev libgtk2.0-dev cmake
}}}

To reduce the build time of OpenCV and add some video libraries you can choose to install these additional libraries:
{{{
sudo apt-get install libjpeg-dev libtiff4-dev ffmpeg libgstreamer0.10-dev libgtk-3-dev
}}}

=== Compiling ===
From the command line you can compile SmartUAV with a make command. While the terminal is pointed to the head {{{/SmartUAV/Software}}} folder type the following to make all:
{{{
make
}}}
This will generate a {{{/build}}} folder where all the compiled files are created along with the {{{CMakeCache.txt}}} which contains all cmake options. Additionally a {{{/bin}}} folder is generated where the executables are generated.

To run SmartUAV, navigate to {{{/SmartUAV/Software/SmartUAV}}} and type the following:
{{{
../bin/SmartUAV
}}}

You can also build SmartUAV from within an editor. We will describe here how to set-up your C++ editor with SmartUAV. We will give the example of Eclipse Luna as this is a popular cross platform multi-purpose editor.

Follow these instructions to install the most recent version of Eclipse for Linux: [http://www.krizna.com/ubuntu/install-eclipse-in-ubuntu-12-04/ Install Eclipse]

SmartUAV is a large project with thousands of lines of code and Eclipse sometimes gets blocked when indexing the project so it is a good idea to change the default Java memory settings. In your terminal enter {{{sudo gedit /opt/eclipse/eclipse.ini}}}. Now edit the last three lines to values like these: 
{{{
-XX:MaxPermSize=1024m
-Xms160m
-Xmx2048m
}}}

Now launch Eclipse, select {{{File->New->Makefile Project from Existing Code}}}. Here you can fill in the name of your project that you like (eg. SmartUAV). Point the "Existing Code Location" to {{{$MYFOLDER/SmartUAV/Softawre}}}, where you replace $MYFOLDER with the folder location of you local svn repository. Select {{{Linux GCC}}} for Indexer Settings and then finish.

From here you can build SmartUAV. To run the program you have to create a new run configuration. Select Run->Run Configurations, once here right click on C/C++ Application and select new and give it a name. Fill in {{{$MYFOLDER/SmartUAV/Softawre/bin/SmartUAV}}} as the C/C++ Application path. In the Arguments tab edit the Working directory to {{{${workspace_loc:SmartUAV}/SmartUAV}}}. 

Now you should be able to launch SmartUAV!

== Windows ==
SmartUAV is stored on an svn server. Windows has several GUI tools to interface with SVN servers. A popular tool for svn on Windows is TortoiseSVN. This is commonly available on TU Delft workstations. If using your own device, you can install it using this link:

[http://tortoisesvn.net/downloads.html TortoiseSVN]

The URL for the repository is {{{https://svn.lr.tudelft.nl/MAVLAB/SmartUAV/}}}

All libraries and dll's needed for Windows is included in the repository so additional libraries should be necessary.

[http://www.cmake.org/download/ Download Cmake]

=== Compiling ===
We will describe here how to set-up your C++ editor with SmartUAV. We will provide an example of getting Microsoft Visual Studio 2012 (MSVC) for Windows users.

First we have to set-up the project solution for MSVC. Launch Cmake and enter {{{$MYFOLDER/SmartUAV/Softawre}}} into the source code input, where you replace $MYFOLDER with the folder location of you local svn repository. Next enter {{{$MYFOLDER/SmartUAV/Software/build}}} for the build binaries input. Click on Configure and enter the version of MSVC you are using, MSVC 2012 is Visual Studio 11. Once this is complete, click on Generate and you are ready to go.

Navigate in your window manager to {{{$MYFOLDER/SmartUAV/Software/build}}} and open the SmartUAV.sln file, this will launch MSVC. In the Solution Explorer right click on SmartUAV/SmartUAV and click on "Set as the startup project". Again right click on SmartUAV/SmartUAV and navigate to properties, here select "Debugging" in "Configuration Properties" and change the "Working Directory" input to {{{$MYFOLDER/SmartUAV/Software/SmartUAV}}}.

With this you should be able to build and run SmartUAV!
