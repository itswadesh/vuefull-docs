---
title: Directory Structure
date: 2019-06-18 06:40:12
---

## Client Directory Structure

``` bash
|   .gitignore
|   nuxt.config.js
|   package.json
|   README.md
|   
+---assets
|       transitions.css
|       
+---components
|       Edit.vue
|       Footer.vue
|       Header.vue
|       Leftmenu.vue
|       List.vue
|       ListImage.vue
|       Loading.vue
|       LoginFormEmail.vue
|       OauthButtons.vue
|       Submit.vue
|       
+---config
|       index.js
|       menu.json
|       
+---filters
|       index.js
|       
+---i18n
|       fr.js
|       hu.js
|       index.js
|       
+---layouts
|       account.vue
|       default.vue
|       error.vue
|       none.vue
|       
+---mixins
|       basic.js
|       index.js
|       
+---pages
|   |   index.vue
|   |   
|   +---account
|   |   |   change-password.vue
|   |   |   forgot-password.vue
|   |   |   index.vue
|   |   |   login.vue
|   |   |   profile.vue
|   |   |   signup.vue
|   |   |   
|   |   \---reset-password
|   |           _token.vue
|   |           
|   +---books
|   |       config.js
|   |       index.vue
|   |       _id.vue
|   |       
|   +---movies
|   |       config.js
|   |       index.vue
|   |       _id.vue
|   |       
|   +---oauth
|   |       success.vue
|   |       
|   +---tasks
|   |       config.js
|   |       index.vue
|   |       _id.vue
|   |       
|   \---users
|           config.js
|           index.vue
|           _id.vue
|           
+---plugins
|       i18n.js
|       nuxt-client-init.js
|       sweetalert2.js
|       validate.js
|       
+---static
|       bg.webp
|       boy.png
|       excel.png
|       favicon.ico
|       
\---store
        auth.js
        index.js
```


## Server Directory Structure

``` bash
|   .env
|   .gitignore
|   package.json
|   prod.env
|   README.md
|   sample.env
|   tsconfig.json
|   tslint.json
|   
+---devops
|       copy.js
|       create.js
|       
+---exports
|       
+---server
|   |   app.ts
|   |   config.ts
|   |   routes.json
|   |   routes.ts
|   |   seed.ts
|   |   tsconfig.json
|   |   
|   +---api
|   |   |   base.ts
|   |   |   
|   |   +---book
|   |   |       config.ts
|   |   |       controller.ts
|   |   |       index.ts
|   |   |       model.ts
|   |   |       
|   |   +---contact
|   |   |       config.ts
|   |   |       controller.ts
|   |   |       index.ts
|   |   |       model.ts
|   |   |       
|   |   +---email
|   |   |       email.controller.ts
|   |   |       index.ts
|   |   |       
|   |   +---lib
|   |   |       email.ts
|   |   |       handlebars-helpers.ts
|   |   |       hbs-helpers.ts
|   |   |       image.ts
|   |   |       index.ts
|   |   |       
|   |   +---movie
|   |   |       config.ts
|   |   |       controller.ts
|   |   |       index.ts
|   |   |       model.ts
|   |   |       
|   |   +---task
|   |   |       config.ts
|   |   |       controller.ts
|   |   |       index.ts
|   |   |       model.ts
|   |   |       
|   |   \---user
|   |           index.ts
|   |           user.controller.ts
|   |           user.model.ts
|   |           
|   +---auth
|   |   |   auth.service.ts
|   |   |   index.ts
|   |   |   
|   |   +---local
|   |   |       index.ts
|   |   |       passport.ts
|   |   |       
|   |           
|   +---components
|   |   \---errors
|   |           index.ts
|   |           
|   +---migrations
|   |       books.ts
|   |       movies.ts
|   |       tasks.ts
|   |       users.ts
|   |       
|   \---public
|           index.html
|           
\---templates
    |   blank.hbs
    |   default.hbs
    |   style.css
    |   
    \---user
            change-password-success.hbs
            change-password.hbs
            reset-password.hbs
            verify.hbs
```