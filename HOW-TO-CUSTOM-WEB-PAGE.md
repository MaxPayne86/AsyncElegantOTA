## Introduction

Find source code of user interface in original ElegantOTA repository [here](https://github.com/ayushsharma82/ElegantOTA/tree/master/ui).

##  How to customize the web page for AsyncElegantOTA library

### Prepare the environment

1. Clone the ElegantOTA library on a folder:  git clone [Click Here](https://github.com/ayushsharma82/ElegantOTA.git)
2. Install npm. On Ubuntu sudo apt-get install npm.
3. On folder ElegantOTA/ui/ open a shell and run the command npm install.

### Change the favicon

1. Convert your favicon.ico to png format.
2. Convert your favicon.png image to base64 (you can use this online tool: https://www.base64-image.de/). You will obtain a code like this one:

```
data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAMAAAAoLQ9TAAABsFBMVEUAAADix+CjY6OzfLJZAFqocauGTpaHT5eNuJk2qFE3qF.
```

3. In file ElegantOTA/ui/public/index.html substitute the line

```
<link rel="icon" href="<%= BASE_URL %>favicon.ico">
```

with the line

```
<link href="data:image/png;base64, iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAMAAAAoLQ9TAAABsFBMVEUAAADix+CjY6OzfLJZAFqocauGTpaHT5eNuJk2qFE3qF" rel="icon" type="image/png" />
```

(containing the image previously encoded).

4. In file ElegantOTA/ui/compress.js substitute the line

```
<link rel=icon href=/favicon.ico>
```

with the line

```
<link href="data:image/png;base64, iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAMAAAAoLQ9TAAABsFBMVEUAAADix+CjY6OzfLJZAFqocauGTpaHT5eNuJk2qFE3qF" rel="icon" type="image/png" />
```

(containing the image previously encoded).

### CHANGE THE TITLE

1. In file ElegantOTA/ui/public/index.html put a title like this  <title> PUT YOUR TITLE  HERE </title> instead of <title><%= htmlWebpackPlugin.options.title %></title>.
2. In the file ElegantOTA/ui/compress.js put a title like this  <title> PUT YOUR TITLE  HERE </title> instead of <title><%= htmlWebpackPlugin.options.title %></title>.


### CHANGE THE LOGO

1. Convert your icon image to base64 (you can use [this online tool](https://www.base64-image.de/)). For example, if your original image is a png you will obtain a code like this:

```
data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAMAAAAoLQ9TAAABsFBMVEUAAADix+CjY6OzfLJZAFqocauGTpaHT5eNuJk2qFE3qF.
```

2. In file ElegantOTA/ui/src/App.vue substitute the line

```
<img width="280px" alt="ElegantOTA" src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPHN2Zy.............nPgo=">
```

with the line

```
<img width="280px" alt="YOUR LOGO HERE" src="data:image/png;base64, iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAMAAAAoLQ9TAAABsFBMVEUAAADix+CjY6OzfLJZAFqocauGTpaHT5eNuJk2qFE3qF">
```

(containing the image previously encoded).

### DELETE THE COFFEE WIDGET

1. In the file ElegantOTA/ui/compress.js delete the line

```
<script data-name="BMC-Widget" async src="https://cdnjs.buymeacoffee.com/1.0.0/widget.prod.min.js" data-id="6QGVpSj" data-description="Support me on Buy me a coffee!" data-message="You can always support my work by buying me a coffee!" data-color="#FF813F" data-position="right" data-x_margin="24" data-y_margin="24"></script>.
```

### After changes, you have to generate the binary web page

1. On folder ElegantOTA/ui/ open a shell and run the command npm run build. It will generate a new elegantWebpage.h file in the folder ElegantOTA/src/.
2. Copy this file and paste it in folder AsyncElegantOTA/src/  (substitute the previous file).
3. Done!
