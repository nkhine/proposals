--
name: anarchically-scaleable-information-system
title;lang=en: Anarchically scaleable information system.
description;lang= en:Proposal for the development of an information system for the Zeitgeist Movement.
version: 0.1
author: Norman Khine
date: Mon Sep 26 09:19:41 CEST 2011
location: 
--

abstract;lang=en:Abstract

Following the TeamSpeak meeting on the [25/09/2011](http://atrium.zmdev.net/globalwebdevelopment/node/340) and the discussions in the [Welcome to Zeitgeist Global Connect: Other Platforms and CMS systems](http://atrium.zmdev.net/globalwebdevelopment/node/330), it is evident that the Zeitgeist Movement requires a fully scalable information system that would allow minimum administration, use of existing infrastructures, minimum costs with an innovative design. The information system, presented here, will attempt to address this and will provide a possible solution which can be tested by the community. 

Currently, the Zeitgeist Community is made up of 200,000 or so members all dispersed and all volunteers, using Blogs or CMS systems that link to content on Facegroup pages, YouTube pages, Tweeter feeds and many other places which will allow the content to be made available. The issue we as a movement is that at the current rate of exponential growth of information, the message will be lost and no action would be taken. It is human nature that if something is difficult to use/understand either we are forced to adapt or we loose interest in it.

The application will be asynchronous and user driven, rather then a synchronous and I/O blocking systems that currently power most Blogs/CMS systems used by the members,  which is built on the LAMP stack, meaning it has a top down approach and is centralized.

The system's main goal is thus to decentralize information storage and the associated matadata for each and every content type and it is the aim of the system to manage this content and to transparently publish it to as many devices as possible. The system does not use one specific platform nor one specific technology, instead it is designed to be adaptable and simple. There will be no requirement for the content provider to have to learn to use the system as the publishing of content must be and will always be integrated within the user's own PC.

The system is based on the working habits of the Open Source movement, put it simply "Open source isn't only for computer geeks. It is the 'intellectual property wing' of social enterprise and probably, globally, its most successful aspect. About three quarters of the internet runs on open source software."[1](http://www.guardian.co.uk/social-enterprise-network/2011/jan/27/learning-from-open-source-geof-cox)


development;lang=en:Development

The proposed system basic requirements are:-
  
  * Server Side: GitHub/ GitHub Pages, Nodejs
  * Client Side: email address, Git
  
  note;lang=en:please note that using GitHub/ GitHub Pages is just a transitional requirement.

Here is an example of a fully functional statically generated blog, which utilises Nodejs to parse the blog entries, index the search results and display them on the blog via javascript. Thus making a static website of just html files, dynamic! [Simon's Blog](http://blog.jodet.com/jekyll-and-node/) all the code for this is located at [https://github.com/simonjodet/blog](https://github.com/simonjodet/blog)

Therefore the initial system will be as follows:

On the main site, you will have a 'Button', (Set-up a chapter), this will open up a form, where the user will input their email, domain name to be used and a geographical location.

Once the form is submitted, the system checks first to see if the email is correct (we can use libraries such as PythonDNS for example to see if the address is valid) if not the system presents an error, then a verification email(localised), is sent to the user with a verification token.

When the user, clicks on this link, the system checks the verification token and if all is ok, it will then connect to GitHub, create a remote repository with the user's email account as the main administrator, build the GitHub pages based on a preset template and push this to the project's gh-pages branch.

In the mean time, whilst this is being processed, the user will have a feed of what is actually happening, on the screen. For example:

1/. Creating Account
2/. Building the core files
3/. Setting up remote file system
etc...

Once everything is built, the user is presented with instructions of what they need to do next. This will include:

1/. Download SSH key to their machine, in order to ensure ability to securely communicate with the system.

2/. Tutorial/Instructions on how to customise this, changing the logo as an example.

3/. Instructions on how to extend and contribute back. For example, if a user wants to localize the template in Swahili, how can they do this, by simply using their favorite text editor.

4/. As soon as a chapter/site is created, this will be available on on all the other sites and if needs be can be also announced on other mediums such as facebook, twitter etc... the timing of the announcement can be scheduled or we can even build a button which will trigger this event in the back-office of the member's chapter.

back-office;lang=en:Back-Office

There is no such thing as back-office, the back-office is just the profile page of the user, where they can change their password, email or re-generate their SSH access keys.

The system proposed here, will sync (at this phase) through GitHub, all the content on the member's allocated folder. For example, a user adds a blog post, they will write this on a text editor and then they will save it on their hard drive. Once all the content has been done, the user will simply need to push this content to their remote repository. i.e. their GitHub account which we created earlier using the API's available.

Similar in the way Dropbox works, when you create an account, you get an application which you install locally and then this creates a folder where you can put content that you want to share. This is then sync'ed with the remote repository, and the user has also access to it, from a web interface.

As soon as a change is made to this remote repository, the system is made aware that this has happened, and this is registered and the information is propagated to all the devices.

import-of-existing-content;lang=en:Import of existing content

There are tools already available which will import and convert back blog entries from Drupal/Wordpress etc... into simple markdown text. We could write scripts which will parse forum posts if needs be and index this information (but at this stage maybe not necessary)

extendability-of-the-system;lang=en:Extendability of the system

The system is designed to ensure that it is never locked down into a specific technology/service, yes there are basic requirements, like using Git to version control each document, Nodejs to be the work horse that communicates between all the interfaces and the remote repositories. The rest will be up to the end user to choose how best they want to utilize the system.

It is hoped that eventually this system is put on FreeNet/DarkNet, thus the reliance on any servers is now fully decentralized. With this in mind, the structure of the 'front-end' is simple static pages mashed together with javascript widgets.

future-studies;lang=en:Future Studies

The development of the system should study the actual content and be able to learn and 'understand how best to push this information to the interested members, tools like the 'Natural Language Toolkit (NLTK), should be employed to manage this data and either presented should the user chooses and learn from it.

We can write a bot, which can then be send out, to search and index all existing documents, videos, images etc... that is connected to the movement.

When there is a result, this is reviewed and either added to the collective knowledge or discarded. Again here we have tools and algorithms which freely available for this task.

skills-requirements;lang=en:Skills requirements

To implement this project, we will need:

programmers with knowledge of java, javascript, python/ruby
system administrator skills with experience in using any flavor of *BSD or *NIX
persons interests or experience in developing or using knowledge based systems
most obviously understand what I am proposing ;)