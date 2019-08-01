---
title: Settings (Vue Fullstack Generator)
date: 2019-06-18 06:40:12
---
## Client Settings

Path: <em>config.js</em> 

### General Variables

``` js
export const API_URL = 'http://localhost:9000' // The port where API runs
export const websiteName = 'CodeNx.com'
export const demo = false // If enabled will not allow user transactions
export const language = 'en' // Changing this will change the default language across the application
export const tokenExpiry = 60 * 60 * 15 // Login validity (15 minutes)
export const typingTimeout = 700 // After this delay the search api will be fired
export const loadingTimeout = 500 // Loading indicator will be shown after this delay
export const userRoles = ['user', 'vendor', 'manager', 'admin'] // This should be in ascending order of authority. e.g. In this case guest will not have access to any other role, where as admin will have the role of user+vendor+manager+admin
export const currency = { symbol: '₹', code: 'INR' }
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
}```
  
### Menu for dashboad and left Sidebar

Path: <em>config/menu.js</em> 

``` js
menuItems: [
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
path: <em>config.js</em>

### User roles
``` js 
userRoles: ['user', 'vendor', 'manager', 'admin'], // This should be in ascending order of authority. e.g. In this case guest will not have access to any other role, where as admin will have the role of guest+user+vendor+manager+admin
```

### Regional settings
``` js
currency: {  symbol: '₹', code: 'INR'},
```

### General Settings

``` js
export const seedDatabase = false; // Seeds database with some demo data when the database is empty
export const staticPath = './../crud-images';
export const uploadDir = staticPath + '/images/';
export const shopName = 'Codenx.com';
export const shopEmail = 'info@codenx.com';
export const emailFrom = 'Customer Service <support@codenx.com>';
export const userRoles: string[] = ['user', 'shipper', 'vendor', 'manager', 'admin']; // This should be in ascending order of authority. e.g. In this case guest will not have access to any other role, where as admin will have the role of guest+user+vendor+manager+admin // Used at auth.service.ts
export const pageSize: number = 40
```

## Environment Settings (Server Module)

``` js
SERVERPORT=9000
DOMAIN=http://localhost:9000

MONGODB_URI=mongodb://username:password@localhost:27017/crud?authSource=admin
SESSION_SECRET=crud-secret

SENDGRID_API_KEY=YOUR_SENDGRID_API_KEY

``` 

## API Level Settings (Server Module)
path: <em>server/api/book/config.ts</em>
``` js
export const modelName = 'Book'
export const fields = {
    name: 'string',
    author: 'string',
    active: 'boolean',
    price: 'number',
    category: 'string',
    image: 'string',
    isbn: 'string',
    weight: 'string',
    releaseDate: 'date'
}
```
