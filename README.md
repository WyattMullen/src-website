# src-website
Markdown and other files needed to help me update website

--------------------------------------------------------------------------------
# Stanford Running Club Website
--------------------------------------------------------------------------------

_Updated by:
Kat Gregory 6/25/18
David Tobin 3/21/11_


--------------------------------------------------------------------------------
# Overview
--------------------------------------------------------------------------------

## 1) Gain admin (and therefore edit) access privilege. 

If you're seeing this, you've already been added as an administrator.
There are instructions in the "Adding New Administers" section as to how to give
other users admin privilege. Remember to pass on access privledge and editing
instructions before you leave the Farm.

## 2) Find the website source. 

The folder containing all files related to the running club website lives in the
Stanford WebAFS system, at /afs/ir/group/runningclub. You can ssh in directly
from terminal by following these steps:

// This prompts for your password and logs you into the AFS system.
`ssh -Y <SUNETID>@myth.stanford.edu`
// This jumps you to the running club website directory.
`cd /afs/ir/group/runningclub`

From here, the folder that you care about is called "WWW". Open it. Each page on
the site has a corresponding html source file. The home page is "index.html".
There are also folders containing, for example, photos, css, and javascript. 

## 3) Edit away! 

You have a few different options as to how to work with the code. They'll be 
covered in more detail in the "Editing Content" section.

_Note that some elements, like the menu and the footer, are repeated in each 
html file. This means that to change, for example, the run times enumerated in 
the footer, you must make that change on every file._

## 4) Commit your changes.

The "Committing Changes" section below contains tips on how to use GitHub to 
keeptrack of changes.

--------------------------------------------------------------------------------
# Editing Content
--------------------------------------------------------------------------------
Again, you can choose between a few different methods of editing the code base:

## 1) Edit locally...
When you edit locally, any changes you make will go live as soon as you save 
the file.

### a) via ssh:
This means that you are working directly in the AFS file system, accessed via 
ssh as described above ("Find the Website Source"). You can simply make changes
in the WWW directory. 

### b) via OpenAFS:
Instead of directly ssh-ing in, I use a combination of Kerberos
and AFS Controller to get the running club folder to act just like a normal file
folder on my computer. This allows me to use Sublime or Atom to edit the files. 
It's not necessary but makes things easier if you're interacting a great deal
with the code. 

## 3) Edit removely via Git:
As an alternative to working within the AFS file system, you can create a
working copy of the code base on your own machine, edit that version, and then
push changes to Git. In this case, your changes won’t go live until you pull
them from AFS.

You can clone a copy of the repository on your own machine via this command:
`git clone https://github.com/katgregory/stanford-running-club.git`


--------------------------------------------------------------------------------
# Commiting Changes
--------------------------------------------------------------------------------
The content of the Running Club website is managed using GitHub, a
version control system.  This will allow us to keep a history of the
changes to the website (for the enjoyment of posterity), and to undo any
accidental changes to the website.

Our repo is located here: https://github.com/katgregory/stanford-running-club
Note that you may have to contact Kat Gregory to gain access.

For a tutorial on GitHub, google it or use this one:
https://guides.github.com/activities/hello-world/

## Before you make changes:
Regardless of whether you're editing locally or remotely, it's a good idea to
make sure that you're looking at the most up-to-date version of the code 
base before making changes. To do this, run:

`git status` // Check if your version is out of date
`git pull` // Refresh with the latest changes

## After you make changes:
After making changes, commit your work with a message that will help you (or
others) understand what this change accomplished.

`git status` // Check that there haven't been any other changes
`git add .` // Add all files that you've modified
`git commit -m "<SHORT MEMO ABOUT WHAT YOU CHANGED>"` // Tag this change with a message
`git push` // Push your changes to the master repo

### If you're working remotely:
In order to see your changes live on the website, you need to go back to AFS 
("Find the website source") and run:

`git status` // Verify everything looks good
`git pull` // Refresh the AFS folder with your new changes

If you get stuck, there is always Google.  Happy hacking.


--------------------------------------------------------------------------------
# Content to Update
--------------------------------------------------------------------------------
Things to keep in mind:

1. Update practice times, if they've changed.

1. Add banners at the start of each year inviting new students to come to open
practice and get a feel for the club.

1. Update race schedule for the season.

1. Solicit updates to the Club Records page using this form: 
http://tiny.cc/new_src_pr. I suggest adding a notification rule to the attached
spreadsheet so that you receive an email whenever someone submits a new record.

1. Update the officers after power changes hands.


--------------------------------------------------------------------------------
# Wishlist
--------------------------------------------------------------------------------

If you've got extra time on your hands:

1. Use Angular (or react) to make this a dynamic site (or at least reduce
duplicated code like the header and footer).

1. Add team photos and bios. Make sure to include alumni too ;)


--------------------------------------------------------------------------------
# Adding New Administrators
--------------------------------------------------------------------------------

New administrators should be added to the runningclub-admins AFS group.

To see the current members of the group,  run:
  `pts membership runningclub-admins`

To add a new admin, run:
  `pts adduser <username> runningclub-admins`


--------------------------------------------------------------------------------
# About
--------------------------------------------------------------------------------

Website created by **Kat Gregory** in 2015.

Used Grayscale template for CSS [Grayscale]
(http://startbootstrap.com/template-overviews/grayscale/)
Copyright 2014 Iron Summit Media Strategies, LLC. Code released under the 
[Apache 2.0](https://github.com/IronSummitMedia/startbootstrap-grayscale/blob/gh-pages/LICENSE) license.

Questions? Or just want to say hi? Drop Kat a line at katg@cs.stanford.edu.
