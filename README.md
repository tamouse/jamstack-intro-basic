# Issus with building JAMStack example #

I ran into some issues following the steps I could catch in the FeM course on JAMStack into. I like missed something crucial.

Here's what I tried, and how I got it to work.


``` shell
$ git clone git@github.com:jlengstorf/jamstack-intro.git
$ cd jamstack-intro/
$ git fetch
$ gco start
$ cd sections/basic/
$ touch index.html
$ emacs index.html # create a very basic html doc
$ git init
$ hub create jamstack-intro-basic
$ git add --all
$ git commit -m 'initial commit'
$ git push -u origin master
$ netlify dev # FAILED with:

◈ Netlify Dev ◈
◈ No dev server detected, using simple static server
TypeError: Cannot read property 'startsWith' of undefined
    at isNetlifyDir (/usr/local/lib/node_modules/netlify-cli/src/commands/dev/index.js:55:14)
    at DevCommand.run (/usr/local/lib/node_modules/netlify-cli/src/commands/dev/index.js:381:31)
    at async DevCommand._run (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/command/lib/command.js:44:20)
    at async Config.runCommand (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/config/lib/config.js:160:9)
    at async Main.run (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/command/lib/main.js:21:9)
    at async Main._run (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/command/lib/command.js:44:20)

$ yarn init -y
$ netlify dev # FAILED with:

◈ Netlify Dev ◈
◈ No dev server detected, using simple static server
TypeError: Cannot read property 'startsWith' of undefined
    at isNetlifyDir (/usr/local/lib/node_modules/netlify-cli/src/commands/dev/index.js:55:14)
    at DevCommand.run (/usr/local/lib/node_modules/netlify-cli/src/commands/dev/index.js:381:31)
    at async DevCommand._run (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/command/lib/command.js:44:20)
    at async Config.runCommand (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/config/lib/config.js:160:9)
    at async Main.run (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/command/lib/main.js:21:9)
    at async Main._run (/usr/local/lib/node_modules/netlify-c

$ netlify init
$ emacs index.html # make a minor change
$ git add -A
$ git commit -m 'initialize package.json, netlify'
$ git push
$ netlify dev # FAILED WITH:

◈ Netlify Dev ◈
◈ No dev server detected, using simple static server
TypeError: Cannot read property 'startsWith' of undefined
    at isNetlifyDir (/usr/local/lib/node_modules/netlify-cli/src/commands/dev/index.js:55:14)
    at DevCommand.run (/usr/local/lib/node_modules/netlify-cli/src/commands/dev/index.js:381:31)
    at async DevCommand._run (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/command/lib/command.js:44:20)
    at async Config.runCommand (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/config/lib/config.js:160:9)
    at async Main.run (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/command/lib/main.js:21:9)
    at async Main._run (/usr/local/lib/node_modules/netlify-cli/node_modules/@oclif/command/lib/command.js:44:20)


$ netlify dev -d . # SUCCESS
```

