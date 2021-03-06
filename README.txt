New in This Release
===================

 - v11.1.1 -
Minor fixes for these issues:
https://jira.duraspace.org/browse/ISLANDORA-246
https://jira.duraspace.org/browse/ISLANDORA-244
https://jira.duraspace.org/browse/ISLANDORA-247

 - v11.1 (2011 Q1) - 

Web-based GUI for creating collections and content models. 
Special thanks to Mark Roy from the University of Manitoba
for contributing this component. To use it: enable the Islandora
Content Modeller module and then go to Administer -> Content
Management -> Islandora Content Modeller to begin creating
collections without having to edit any XML datastreams. 

PDF content model includes integration with Google's online PDF
preview service. 

Tabbed interface using JQuery UI Tabs 

Ant script to automatically configure Fedora to connect to
Drupal to perform authentication. 

CCK PID Field module - Lets you associate a Fedora object with
a Drupal node, to enable comments, voting, ratings and any other
Drupal module that operates on node content.

Git Submodules
==============

If you downloaded this package by cloning the islandora-dist git
repository you will need to retrieve the submodules by running:

 $ git submodule init
 $ git submodule update

Getting Started
===============

The fedora_repository module allows Drupal users to view and manage
digital objects stored in a Fedora repository. For more information
about this project,  see the the Islandora Page at UPEI:

http://islandora.ca/

An installation and getting started guide is located at:

https://wiki.duraspace.org/display/ISLANDORA/Islandora+Guide

Before the Digital Repository module can interact with the Fedora
repository you must install the included servlet filter .jar file.
See the file servlet_filter/servlet_filter_README.txt for instructions.

The Fedora Digital Repository module depends on two other modules, 
JQuery UI Tabs (http://drupal.org/project/tabs) and ImageAPI 
(http://drupal.org/project/imageapi). respectively. Download and
unzip those into your site's modules folder before enabling the 
Fedora Digital Repository module.

Custom content types may require additional resources.  The supplied 
Large Image Collection will requite Kakadu's ImageMagick be installed 
on your system.  Kakadu can be found at:

http://www.kakadusoftware.com/index.php

Some SimpleTest files have been included to test your installation.
See the file testing/README_testing.txt for instructions on running
the tests.
