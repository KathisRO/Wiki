~start
	Hello Dev's and Wiki editors. This is going to be a page to explain how the wiki works, and what sort of magical syntax we can do with obsidian. 
	
Firstly you will notice that everything is between a ~start and end ~ tag. These will be completely ignored byt the site. But not from obsidian. 
I have a space after the end  so it doesn't end earily. 

[[#Internal Links]]
[[#Headers]]
[[#Emphasis]]
[[#Tags]]
[[#Spoiler Collapsible]]
[[#Lists]]
[[#Tables]]
[[#The Double edge of HTML]]


# Internal Links
Use them for placing internal links into the page, that we want to still see connected in the graph view on obsidian. (For example if you want to go super pretty and use html. Links inside will not be shown on the graph view, though our tools are able to pretty much pick up the links easily enough.)  

DO NOT use ``<a href>`` in the html tags. The wiki doesn't care about it, and will simply ignore it during pharsing. That is another good reason to have the links in the ~start and end ~ block.  If you need to refer to an external page (not included in the wiki) use [display](http://www.google.com)


To make a link simply put it between two square brackets [[index]] link this. If you want it to display a different word but still link you can go [[index|display]]  On the side you should see a few folders. Those are linked by putting it like folder/NameOfFile  The site will ignore the folders names and only focus on the NameOfFile, though the url will still display these folder. (maybe I'll beable to fix that at some point) 

If you want to link further on a page put a # in the tag like [[#index]]  However the name must match up to the same header.  If you want to link to another page's at a header, use [[Index#group 3 heading 3 ]]

```
![[image.png]] <- this will pull from the images folder on the wiki, obsidian will search the entire wiki to figure out which image you are refering to.

[[Link to inner page]] <- This will make a link to another page on the wiki.

[[Link to inner page|display]] <- This will make a link to another page on the wiki, but have a different display text. 

[display](http://www.google.com)  <- This will show the display text, but link to the url in the brackets. 

[[#header]] <- This will show a link without the #, and jump to that header on the current page.

[[page#header]] <-This will link to the page with the header, it will show the Header tag. 

[[page#header|display]] <- this will show the display, and jump to the page's header that matches. 

```

Note: If a page doesn't exist in github, or the site cannot find the page, it will display the link as plain text. Thus making it hard for players to find dead links. Obsidian will still see the dead links however.


# Headers
Headers are done like so.
```
# heading 1
## heading 2
###  heading 3 
#### heading 4
##### heading 5
###### heading 6
```

You can only support up to 6 levels. 
Putting it like
```
#header 
```
Will actully make a markup tag.  This is still treated as a Header 1 in the wiki, but obsidian will not see it as such. 

Though it is possible to put links in the header, don't.. the parcer won't know what to do with it. 

# Emphasis
*Italic text*, **Bold Text**, ***Italic bold text***, <u>Underline</u>, ~~stricked~~
```
*Italic text*, **Bold Text**, ***Italic bold text***, <u>Underline</u>, ~~stricked~~
```

Unfrotuantely the underline doesn't have it's own special markdown symbol, but you can still use html tags to acheive it. 

# Tags
Tags are useful for us, I might make the wiki have it searchable by tags at some point, but I don't feel like that will be needed, if we're allow them to search the entire page. 

```
---
tags:
  - Town
  - Midgard
  - Guilds
---
```

Tags are made with 3 hyphans, the word tag: and then a hyphan for each tag. Closed off by 3 hyphans. 

Tags are useful for obsidian since you can search and color by tags in the graphic view. Also in the view mode you can click on the tag and it will show other pages that the tag is in. 

The Wiki will not show tags. Though we can make the database STORE the tags for faster searchability later. 
	
# Spoiler / Collapsible

The syntax for this is basically a `` > `` Obsidian will show it as a box in the reader, you cannot collapse it in obsidian, but the site will treat this as a collapsible box. 
>it looks like this
you can do multiple lines
and it will contiune. 

But you need to have a clean line after the block. Otherwise it will thing it all needs to be in the same box. 

>You can also go like
>this, but these will
>appear on the same line on the site.

Note: to put a box inside of another box you need to add additional ``>`` 
```
> box one
>> box two
>>> box three

^ this requires an empty line to end the boxs. 
```

Note: It might not be possible to put a collapse box inside a table.

# Lists

There are two types of lists that you can use, numeric and bullets. 

Bullet lists are done like so
```
- Item 1
- Item 2
  - Item 2a
  - Item 2b
  
* Item 1
* Item 2
	* Item 2a
	* Item 2b

+ Item 1
+ Item 2
	+ Item 2a
	+ Item 2b
```
Though the bullets do work with - * and + It may be better to use - or + since * is used for formating like Bold and italics. Also don't interchange the symbol you use, stick with 1 type.

When you indend the bullet will change shape to help readability. The first level is ●. The second is ○, and any others after will be ■

Numeric lists can be done like so.
```
1. Item 1
2. Item 2
  1. Item 2a
  2. Item 2b
  
1. Item 1
1. Item 2
	1. Item 2a
	1. Item 2b

1. Item 1
8. Item 2
	5. Item 2a
	2. Item 2b

```
The order of the numbers don't seem to matter, just that it started with a number followed by a period followed by a Space. 

Notes: That if your unorder list starts with a number followed by a period you need to put a \ slash. 

```
- 2005\. The start of the server.
- 2018\. The year Kathis became server owner.
```

# Tables
Tables are used to help the information look more smoother. 

```
First Header | Second Header
------------ | ------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column
```

The first row will always be the header.  each line (enter) will make a new row. Under the headers require  
```
 |
- | -
 |
```
Notice the space after before the first pipe. If there are no headers, the wiki will make the table borderless. Though obsidian does not reflect this.  Putting a space between the pipes will make an empty cell. You can put as many - as you wish. It only effects readability. 

Further you can also use html if you desire. If you don't include the border=1 however it will default to no borders. 

# The Double edge of HTML

Though html is amazing and powerful, Obsidian will not show normal markup languages renders while encased in html. The Site however can still function properly. Because it's looking for patterns in the string that was sent via github. So do remember this.

# Special Functions
To inidicate a function you need to 


# Planned features to come. 
by putting (I/#) this will be searched in the wiki to replace with some item data, such as it's small icon, and a link to it's page, it will replace the text with it's SQL name. 

(M/#) will also be the same where it will pull from the monster data from the sql. 




end~