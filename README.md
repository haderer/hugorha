# hugorha

Hugo theme for lorhammer.

Live demo here : https://itksource.github.io/hugorha/

## Hugo project

https://gohugo.io/

## Use hugorha

```bash
cd themes
git clone https://github.com/itkSource/hugorha.git
```

Add `hugorha` has theme in your config.toml.

All your page of first level menu must have `menu: "main"` in there meta.

In your config you must have :

```toml
[params]
# The title of your homepage (to be rendered in /)
homePageTitle = "Hugorha"
# The logo path (placed in /static) and name with the extention
logoFileName = "images/headerLogo.svg"
# Generate JSON to have runtime search
[outputs]
    home = [ "HTML", "RSS", "JSON" ]
    page = [ "HTML" ]
# Add git infos on each files (last modified author and date)
enableGitInfo = true
# Favicons links
favicons = [
    '<link rel="apple-touch-icon" sizes="57x57" href="/images/favicon/apple-icon-57x57.png">',
    '...'
]

    [params.header]
    # The links (label, src) rendered in top /right site
    links = [ [ "itk", "http://www.itk.fr" ], [ "ForkMe ImFamous", "http://gitlab.com/itk.fr" ] ]

    [params.footer]
    # The copyright rendered in footer
    copyrightHTML = "Copyright &#xA9; 2013 John Doe. All Rights Reserved."


    [params.css]
    # The font files path (placed in /static) and name with the extention. Only need WOFF2 and WOFF format [Default : sans-serif]
    specialFontName = "font/minspsw"

    # the main color [Default : #60adea]
    mainColor = "#266ed4"
    # The text color on the main color (like the menu) [Default : #FFF]
    textColorOnMainColor = "#fff"

    # if gradient 1 and 2 are set, the background of menu and footer will be a gradient
    gradient_1 = "#266ed4"
    gradient_2 = "#266ed4"

    # the color of the logo text [Default : #468ef4]
    logoColor = "#fff"
    # If true the Site Name in the header will be only outlined with the color [Default : false]
    siteNameBorder = false

    # the header background color [Default : #FFF]
    headerBg = "#266ed4"
    # the header text color [Default : #222]
    headerTextColor = "#FFF"
    # the header padding [Default : 20px]
    headerPadding = "40px"

    # the background color [Default : #FFF]
    bgColor = "#fff"
    # The text color [Default : #222]
    textColor = "#222"

    # Display the menu as fancy tabs [Default : false]
    menuAsTab = "true"

    # Color of the alert block [Default : red]
    alertColor = "red"

```

> Full configuration can be found in [example/config.toml](https://github.com/itkSource/hugorha/blob/master/example/config.toml)

## How it looks like ?

Without any CSS params :
[![Hugorha default skin](static/images/hugorha-default.png)](static/images/hugorha-default.png)

With the CSS param given above :
[![Hugorha exemple skin](static/images/hugorha-skin.png)](static/images/hugorha-skin.png)


## Dev on hugorha

* Install [hugo](http://gohugo.io/overview/installing/)
* Run command :

```bash 
hugo server -wDs ./example
```

* Open browser [localhost:1313](http://localhost:1313/)

## Publish new gh-pages

```bash
HUGO_BASEURL="https://itksource.github.io/hugorha/" hugo -s ./example
git add -A .
git commit -m "deploy new gh-pages"
git push origin master
```