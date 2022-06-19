~start
	Hello Dev's and Wiki editors. This is going to be a page to explain how the wiki works, and what sort of magical syntax we can do with obsidian. 
	
Firstly you will notice that everything is between a ~start and end~ tag. These will be completely ignored byt the site. But not from obsidian. 

Use them for placing internal links into the page, that we want to still see connected in the graph view on obsidian. (For example if you want to go super pretty and use html. Links inside will not be shown on the graph view, though our tools are able to pretty much pick up the links easily enough.) 

DO NOT use ``<a href>`` in the html tags. The wiki doesn't care about it, and will simply ignore it during pharsing. That is another good reason to have the links in the ~start and end~ block. 


To make a link simply put it between two square brackets [[index]] link this. If you want it to display a different word but still link you can go [[index|display]]  On the side you should see a few folders. Those are linked by putting it like folder/NameOfFile  The site will ignore the folders names and only focus on the NameOfFile, though the url will still display these folder. (maybe I'll beable to fix that at some point) 

If you want to link further on a page put a # in the tag like [[#index]]  However the name must match up to the same header. 

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
Will actully make a markup tag. This isn't really useful for the site. and will still show up like a 
	
	
	

end~