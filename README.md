# Navi

## A minimal navigation generator script for static sites written in Python3.

![Navi :)](https://orig00.deviantart.net/4f58/f/2016/105/8/9/the_legend_of_zelda_navi_pagedoll_by_gabagarb-d9z1que.gif)

### 1.) Setup the script: 

Place your static web files in the "web" directory (or change the "web_root" variable in "navi/config.py" to point to another directory). Change the ```url``` variable in "navi/config.py" to match the URL of your site.

### 2.) Modify your pages: 

Modify each page to contain the HTML ```<navigation>navigation<navigation>``` in the location that you want the navigation to be generated.

### 3.) Edit the pages list:

Edit the "pages" dictionary in "navi/page_list.py" to contain your page names and locations (each page must be added here manually for security). Use the Python syntax ```pages.update({"Page ID (Name/Title)":"path/to/file.html"})``` to add a new page where the KEY is the page ID (the link text as a string) and the VALUE is the file location as a sting. If you want a file to have its navigation updated but the file itself should not be included in the navigation, simply give it a NULL ID like this: ```pages.update({"NULL":"path/to/file.html"})```

**NOTE:** the ```web_root``` is automatically prepended to the path. This script assumes that all files that it needs to work with are in ```web_root```.  

### 4.) Customize your navigation template:

Edit "navi/nav-template.html" to suit your needs. This is the template file that will be used to generate the navigation on all of your pages. You can use any HTML/CSS/JS here that you need. Use the syntax: ```{{Page ID}}``` to specify where each link should go in the layout. The rest will be automated. 

### 5.) Run the script:

Run "navi/navi.py" from the CLI to replace the pages. Something like ```python3 navi.py```. The new files will output to the "navi/OUTPUT" directory to ensure the script is fail-safe. You can now test the files in your output folder and if everything looks good, merge it back into your webroot. 
