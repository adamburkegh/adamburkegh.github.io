---
layout: post
title: ProM Development Setup with JDK8
tags: prom jdk8 eclipse
---

These are the steps I followed to checkout, compile and run ProM 6.9 as a project in Eclipse. I followed the steps here:
<https://svn.win.tue.nl/trac/prom/wiki/setup/HowToBecomeAProMDeveloper>

... but a few things have changed. I also had a new machine I was working with, which is always good for catching environmental setup assumptions.

## Setting up the ProM development environment with Java 8

### Install JDK

Download and install the latest Oracle Java Development Kit (JDK) version 8. This was jdk 1.8.0u251 for me. This is the current suggested environment for ProM development. 

I prefer to put development tools under their own dedicated area, like `c:\working\tools\jdk1.8.0u251`, but it should work when installed in the default location.

The Java Runtime Environment (JRE) comes bundled with the JDK.

There are a number of Java versions after 8 (current is actually 14). It's possible to run under later JREs but I found things didn't work out of the box when developing with them. More notes on this at the end. I also saw problems with the OpenJDK, but didn't spend much time troubleshooting.

### Install Eclipse

Install Eclipse, an open source IDE for Java and other things. I installed 2020-03 (4.15.0). Eclipse requires a JRE.

### Install Ivy

Install the IvyDE Eclipse plugin. Ivy is a dependency manager used by ProM.

In Eclipse, choose Help -> Install New Software -> Add ... -> 
	<http://www.apache.org/dist/ant/ivyde/updatesite>

Select the IvyDE plugin and install. You may have to restart Eclipse after install.

IvyDE is on the Eclipse marketplace at 
	<https://marketplace.eclipse.org/content/apache-ivyde%E2%84%A2>
... but I found this didn't work with the latest version of Eclipse. Hence the install site approach above.

The home of the Ivy project is <https://ant.apache.org/ivy/ivyde/index.html>


### Install Subclipse

Install the Subclipse Eclipse plugin. Subclipse integrates Eclipse with Subversion. Subversion is the version control system used by ProM.

In Eclipse, choose Help -> Install New Software -> Add ... -> 
	<https://dl.bintray.com/subclipse/releases/subclipse/latest/>

Choose Core SVNKit Library and Subclipse and install.

You may have to restart Eclipse after install.

The home of the Subclipse project is now <https://github.com/subclipse/subclipse>


### Checkout ProM

In Eclipse, File -> New -> Project -> Other -> SVN -> Checkout Projects from SVN

Create a new repository location
<https://svn.win.tue.nl/repos/prom>

Browse to `Packages/Workshop/Trunk`

Next -> Check out as a project in the workspace

Keep the project name Workshop as it makes some later steps easier

-> Finish


### Build ProM

Once the project has finished checking out, right click on `ivy.xml` -> Add Ivy Library

If this works, it will download many libraries. This will show in the bottom right "Console" pane.

If not, you can choose Project -> Build All.

If the build step worked, under the Problem tab you should see no Errors and, at time of writing, 8 warnings, mostly about generics.


### Run ProM

In Eclipse, choose the Play button -> ProM with UITopia

If this works, it will download many packages. This will show in the bottom right Console pane.

When it is finished, you will see the main ProM screen.

At this point the environment should be ready.


## Later JDK versions

There are some changes already made to ProM to run under Java 9 and later. I found some problems building under JDK 14, even with the Java compiler version set to Java 9. These seem to be around XML libraries no longer being bundled with Java in Java 9 onwards.  There is more detail at the [ProM site](http://www.promtools.org/doku.php?id=troubleshooting:start) about changes to the runtime. These aren't quite enough for compile-time, but as it's not runnning on my machine right now, I'll save that for another post.


## Update 20 July

The ProM developers have folded the updated links back into their documentation on the [ProM wiki](https://svn.win.tue.nl/trac/prom/wiki/setup/HowToBecomeAProMDeveloper).


