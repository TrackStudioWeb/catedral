VTEX Speed
=====

VTEX Store development tools - reverse proxy, compilation, minification, optimization and more!

## Presentation - VTEX Day 2014

Watch a presentation about VTEX Speed here (pt-BR): http://gadr.github.io/presentations/vtex-day-2014/#/

## Pre-requisites

* Node - http://nodejs.org/
* Git - http://git-scm.com/

After installing node, use `npm` to install the Grunt command line application.

    npm install -g grunt-cli
    
If you are using Windows, remember to put `git` on your PATH or use the git bash included in installation.

## Install

Clone this repo or download and unzip it.

## Quick Start

Enter the folder you cloned or downloaded, install dependencies and run `grunt`:

    cd speed
    npm install
    grunt --verbose

**Advanced:** You can easily change the proxy port by setting the PORT environment variable, e.g. `PORT=9000 grunt`

First, open your browser here to authenticate:  

http://your-store-account-name.vtexlocal.com.br/admin/Site/Login.aspx

Then, open a normal page, like your home:

http://your-store-account-name.vtexlocal.com.br/?debugcss=true&debugjs=true

**Important**  You should replace `your-store-account-name` with the accountName of your store. Who would guess, huh?

Now, copy a CSS file from that site over to your `src/` folder.
We already have `src/arquivos/style.css` there as an example.

Go ahead and add a new rule to that file:

    body {
        background: black;
    }

Nice! Live Reload has reloaded that stylesheet for you.

## Features

All files in `src/` are compiled, optimized and copied to `build/` when you run `grunt`.

You can further configure this process editing `Gruntfile.coffee`.

Currently supported:

- LiveReload of assets in HTTP and HTTPS
- Coffee compilation
- LESS compilation
- JS and CSS Minification

But, hey, there's more!

## Discover new Grunt plugins

There are a **ton** of available Grunt plugins for your every need.

Go to http://gruntjs.com/plugins for a complete list.

If you think there's a plugin that's great for everybody, why don't you [fork this repo and open a pull request](https://github.com/vtex/speed/fork)?

## Advanced options

If you want to open the same store every time, you can add an `accountName` property to your `package.json` file:

    "accountName": "your-store-account-name"

When `grunt` runs, this store will open automatically.  
If you wish, you may delete that key and grunt will not open any address.

## Feedback

We always want to hear you! Please report any problems to the issues page:

https://github.com/vtex/speed/issues

## FAQ

### What is `ECONNRESET`?

The HTTP response socket hung up before sending a complete reply.  
You probably manually stopped a request on your browser.  
Thus, the proxy shouted: "I was receiving a response and it stopped abruptly!"
