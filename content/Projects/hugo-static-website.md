---
title: "Hugo Static Website on GitHub"
date: "2023-08-01"
description: "Introduction to Hugo"
tags:
- linux
- hugo
ShowReadingTime: "True"
toc: "true"
---

# Hugo Install and Configurations

    $ sudo dnf install hugo


### Starting Hugo Configurations

    ~$ mkdir hugo-blog
    ~$ cd hugo-blog
    ~$ hugo new site .
    ~$ nano .gitignore

Create a public file to store websire data
```
    public/
```
Close using: (ctl+x+y+enter). Now move to the next step, remember we are still on the same directory.
```
    ~$ git init
    ~$ git add .
    ~$ git status
    ~$ git commit -m "first commit"
    ~$ git branch -M main
    ~$ git remote add origin https://github.com/your-username/hugo-blog-config.git
    ~$ git push -u origin main
```
### Theming

     # we are located in hugo-blog folder
    ~$ ls
     |themes  README.md   data    static  layouts archetypes  content config.toml|
    ~$ cd themes/
     # pick any theme of your choice and place the theme url. In my case I'll use Coder
    ~$ git clone https://github.com/luizdepra/hugo-coder.git
    ~$ cd ..
    ~$ nano config.toml

    baseURL = "http://www.example.com"
    title = "The Simple Linux Theory"
    theme = "hugo-coder"
    languageCode = "en"
    defaultContentLanguage = "en"
    paginate = 20
    enableEmoji = true
    # Enable Disqus comments
    # disqusShortname = "yourdiscussshortname"
    
    [markup.highlight]
    noClasses = false
    
    [params]
    author = "Rob Alicea"
    # license = '<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">CC BY-SA-4.0</a>'
    description = "journey from a tech enthisiast about linux, privacy, smart homes and other things about tech"
    keywords = "blog,tech enthusiast,linux"
    info = ["Professional Fitness Trainer", "Tech Addict"]
    avatarURL = "images/profile.jpg"
    #gravatar = "john.doe@example.com"
    dateFormat = "January 2, 2006"
    since = 2022
    # Git Commit in Footer, uncomment the line below to enable it
    commit = "https://github.com/luizdepra/hugo-coder/tree/"
    # Right To Left, shift content direction for languagues such as Arabic
    rtl = false
    # Specify light/dark colorscheme
    # Supported values:
    # "auto" (use preference set by browser)
    # "dark" (dark background, light foreground)
    # "light" (light background, dark foreground) (default)
    colorScheme = "auto"
    # Hide the toggle button, along with the associated vertical divider
    hideColorSchemeToggle = false
    # Series see also post count
    maxSeeAlsoItems = 5
    # Custom CSS
    customCSS = []
    # Custom SCSS, file path is relative to Hugo's asset folder (default: {your project root}/assets)
    customSCSS = []
    
    # Custom JS
    customJS = []
    
    # Custom remote JS files
    customRemoteJS = []
    
    # If you want to use fathom(https://usefathom.com) for analytics, add this section
    # [params.fathomAnalytics]
    # siteID = "ABCDE"
    # serverURL = "analytics.example.com" # Default value is cdn.usefathom.com, overwrite this if you are self-hosting
    
    # If you want to use plausible(https://plausible.io) for analytics, add this section
    # [params.plausibleAnalytics]
    # domain = "example.com"
    # serverURL = "analytics.example.com" # Default value is plausible.io, overwrite this if you are self-hosting or using a custom domain
    # outboundLinksTracking = true
    # fileDownloadsTracking = true
    
    # If you want to use goatcounter(https://goatcounter.com) for analytics, add this section
    # [params.goatCounter]
    # code = "code"
    
    # If you want to use Cloudflare Web Analytics(https://cloudflare.com) for analytics, add this section
    # [params.cloudflare]
    # token = "token"
    
    # If you want to use Matomo(https://matomo.org) for analytics, add this section
    # [params.matomo]
    # siteID = "ABCDE" # Default value is "1", overwrite this if you are cloud-hosting
    # serverURL = "analytics.example.com" # For cloud-hosting, use provided URL, e.g. example.matomo.cloud
    
    # If you want to use Google Tag Manager(https://analytics.google.com/) for analytics, add this section
    # [params.googleTagManager]
    # id = "gid"
    
    # If you want to use Yandex Metrika(https://metrika.yandex.ru) for analytics, add this section
    # [params.yandexMetrika]
    # id = "gid"
    
    # If you want to use Application Insights(https://azure.com/) for analytics, add this section
    # [params.applicationInsights]
    # connectionString = "connectionString"
    
    # If you want to use microanalytics.io for analytics, add this section
    # [params.microAnalytics]
    # id = "ABCDE"
    # dnt = "false" # respect DNT tracker, "true" by default
    
    # If you want to use Pirsch(https://pirsch.io) for analytics, add this section
    # [params.pirsch]
    # code = "ABCDE"
    
    # If you want to implement a Content-Security-Policy, add this section
    # [params.csp]
    # childsrc = ["'self'"]
    # fontsrc = ["'self'", "https://fonts.gstatic.com", "https://cdn.jsdelivr.net/"]
    # formaction = ["'self'"]
    # framesrc = ["'self'", "https://www.youtube.com"]
    # imgsrc = ["'self'"]
    # objectsrc = ["'none'"]
    # stylesrc = [
    #   "'self'",
    #   "'unsafe-inline'",
    #   "https://fonts.googleapis.com/",
    #   "https://cdn.jsdelivr.net/",
    # ]
    # scriptsrc = [
    #   "'self'",
    #   "'unsafe-inline'",
    #   "https://www.google-analytics.com",
    #   "https://cdn.jsdelivr.net/",
    # ]
    # prefetchsrc = ["'self'"]
    # # connect-src directive – defines valid targets for to XMLHttpRequest (AJAX), WebSockets or EventSource
    # connectsrc = ["'self'", "https://www.google-analytics.com"]
    
    [taxonomies]
    category = "categories"
    series = "series"
    tag = "tags"
    author = "authors"
    
    [[params.social]]
    name = "Github"
    icon = "fa fa-2x fa-github"
    weight = 1
    url = "https://github.com/thesimplelinuxtheory/"
    
    [languages.en]
    languageName = ":us:"
    
    [[languages.en.menu.main]]
    name = "About"
    weight = 1
    url = "about/"
    
    [[languages.en.menu.main]]
    name = "Blog"
    weight = 2
    url = "posts/"
    
    [[languages.en.menu.main]]
    name = "Projects"
    weight = 3
    url = "projects/"
    
    [[languages.en.menu.main]]
    name = "Contact me"
    weight = 5
    url = "contact/"


## Start up server

    $ hugo server -w


# Publish on Github

    ~$ cd ..
    ~$ git clone https://github.com/thesimplelinuxtheory/thesimplefitnesstheory.github.io.git
    ~$ cd thesimplelinuxtheory.github.io
    ~$ git pull origin main
    ~$ cd ..
    ~$ cd hugo-blog
    ~$ hugo -d ../thesimplefitnesstheory.github.io
    ~$ cd ..
    ~$ cd thesimplefitnesstheory.github.io
    ~$ git status
    ~$ git add --all
    ~$ git commit -m "initial commit"
    ~$ git push origin master




![New Linux User](/img/logo1.svg)
