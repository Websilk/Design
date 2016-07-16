# Websilk / Design
Design related files used for the Websilk CMS platform found @ http://www.github.com/Websilk/Home

### How to add icons to the icon SVG sprite

There is a published sprite with 76+ SVG icons embedded in the file, located @ `/wwwroot/images/editor/icons.svg` within the Websilk CMS platform repository. In order to properly add or update icons to the sprite, you must follow the steps below

* create your sprite and import the vector image into Adobe Flash CC
* make sure the document dimensions for your Flash project is the exact bounds of the vector
* convert the vector into a Movie Clip
* open the movie clip and add a new layer above the icon layer. Create a white, transparent box overlapping the icon. This will ensure that the icon is clickable on the web page.
* exit the movie clip, going back into the main scene (Scene 1), then choose from the menu, `File > Export > Export Image...` and choose "SVG image" as the file type. Make sure to save the file in the `/Editor/icons` folder within this Websilk/Design repository
* copy the file into the `/SVG/test/src` folder within this repository
* open a command window, cd into /SVG folder, and run the command: `gulp svg`
	
Note: Make sure you have gulp installed. Also, make sure you run the command "npm install gulp" into the SVG folder

* open the newly generated file from `/SVG/test/dest/src.svg`, and replace the first line of code with the following

    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd"><svg xmlns="http://www.w3.org/2000/svg">
    
    <style type="text/css">
    path:not(.svg-nocolor){fill:currentColor}
    use:not(.svg-nocolor):visited{color:currentColor}
    use:not(.svg-nocolor):hover{color:currentColor}
    use:not(.svg-nocolor):active{color:currentColor}
    </style>
	
* copy the contents of the file `/SVG/test/dest/src.svg` and replace the contents of the published sprite @ `/wwwroot/images/editor/icons.svg` within the Websilk CMS platform repository. (http://www.github.com/Websilk/Home)