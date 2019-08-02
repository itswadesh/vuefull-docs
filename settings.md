---
title: Settings (Vueful)
date: 2019-06-18 06:40:12
---
## Client Settings
Path: <em>config/index.js</em> 

### User roles

::: warning User Roles of the app in ascending order of authority
  e.g. In this example `user` will not have access to any other role, where as `admin` will have the role of `user+vendor+manager+admin`
:::

``` js 
userRoles: ['user', 'vendor', 'manager', 'admin'] 
```

### Regional settings

::: warning Language & Currency
  Changing this will change the default language and currency across the application
:::

### Timeouts

::: warning Time Validity
  Used for search, loading, login token
:::

``` js 
export const tokenExpiry = 60 * 60 * 15 // Login validity (15 minutes)
export const typingTimeout = 700 // After this delay the search api will be fired
export const loadingTimeout = 500 // Loading indicator will be shown after this delay
```

### Common website header

::: warning Will be applicable to all pages across the vuefull-client
  Used for search, loading, login token
:::

``` js 
export const head = {
    titleTemplate: '%s - ' + websiteName,
    htmlAttrs: { lang: language },
    meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1, user-scalable=no' },
        { 'http-equiv': 'x-ua-compatible', content: 'ie=edge' }
    ],
    link: [
        { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css?family=Oswald:300,400,500,700|Material+Icons' }
    ]
}
```

### General Variables

``` js
export const API_URL = 'http://localhost:9090' // The port where API runs
export const websiteName = 'Vuefull'
```
  
### Menu for dashboad and left Sidebar
::: warning Path: <em>config/menu.js</em> 
:::


``` js
[
    {
        "title": "Dashboard", // Name
        "href": "", // Link
        "icon": "dashboard", // Icon
        "authenticate": "user", // The role who can access this menu
        "color": "#1F7087", // Color of the menu at dashboard
        "dashboard": false // Whether it should be shown at dashboard
    },
    {
        "title": "CRUD"
    },
    {
        "title": "Books",
        "href": "books",
        "icon": "book",
        "authenticate": "user",
        "color": "#952175",
        "dashboard": true
    },
    {
        "title": "Movies",
        "href": "movies",
        "icon": "movie",
        "authenticate": "user",
        "color": "#385F73",
        "dashboard": true
    },
    {
        "title": "Tasks",
        "href": "tasks",
        "icon": "folder_open",
        "authenticate": "user",
        "color": "pink",
        "dashboard": true
    }
],
```  

## Server Settings
path: <em>server/config.ts</em>

### User roles

::: warning path: <em>server/config.ts</em>
 User Roles of the app in ascending order
:::

``` js 
userRoles: ['user', 'vendor', 'manager', 'admin'] // This should be in ascending order of authority. e.g. In this case user will not have access to any other role, where as admin will have the role of user+vendor+manager+admin
```

### Image settings

::: warning path: <em>server/config.ts</em>
 Images are stored generally outside of the applicaton folder
:::

``` js
export const staticPath = './../vuefull-images'
export const uploadDir = staticPath + '/images/'
```

### Email settings

::: warning path: <em>server/config.ts</em>
 These email info will be used while sending `password reset`, `forgot password` and `change password` emails
:::

``` js
export const shopName = 'Vuefull'
export const shopEmail = 'Admin <admin@codenx.com>'
export const emailFrom = 'Customer Service <support@codenx.com>'
```

### General Settings

::: warning path: <em>server/config.ts</em>
&nbsp;
:::

``` js
export const seedDatabase = false; // Seeds database with some demo data when the database is empty
export const pageSize: number = 40 // pageSize for each api request
```

## Environment Settings (Server Module)

::: warning path: <em>.env</em>
 Here we specify secret credentials which will be different for local and server
:::

``` js
SERVERPORT=`9090` // The webapp runs in this port
MONGODB_URI=`mongodb://username:password@localhost:27017/vuefull?authSource=admin` // Database username, password, port, database name, auth data source name
SESSION_SECRET=`vuefull-secret` // User session secret
SENDGRID_API_KEY=`YOUR_SENDGRID_API_KEY` // Sendgrid API KEY for emails

``` 
Reference: <a href="https://sendgrid.com/docs/ui/account-and-settings/api-keys/">https://sendgrid.com/docs/ui/account-and-settings/api-keys/</a>
## API Level Settings (Server Module)
