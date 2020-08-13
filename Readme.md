# HTMLX Pre-Processor

When designing complex webpages, it becomes important to reuse components and make the pages modular.  For e.g. instead of repeating same footer code on all webpages, it makes more sense to write a footer.html file and include it in all your webpages.

On server-side most web frameworks support this using {{include}} statements; however this is not easily available on client side.  

HTMLX python based pre-processor that allows you to write HTML files and use dynamic statements like `##include footer.html` Which then generates html files in the dist folder without any JS dependencies. 

## Install Dependencies

```bash
pip install watchdog
```

## Usage
Download the HTMLX.py and place it in your project folder 
```
project_folder
|   htmlx.py
|───static
|   |   
|   |   index.htmlx
|   |   about.htmlx
|   |   footer.html
    |───dist
    |   |   index.html
    |   |   about.html
```

1. Create  a folder called static. Inside this folder create files called index.htmlx   about.htmlx  footer.html
2. Open htmlx files in any text editor, and inside body tags include footer.html using 
`
##include footer.html
`

```bash
cd project_folder
python htmlx.py -c static/  -m prod
```

## Options
Arguments

-m (Mode):  Debug or Prod mode. In prod mode, it strips out all console.log statements

-w <folder>: Watch folder for changes to all .htmlx files and automatically compile to generate results in dist folder

-c <folder>: Compile the folder and generate files in dist


## Known Issues
Currently works only with Python2
