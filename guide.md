---
title: Vuefull Usage Instructions (Guide)
date: 2019-06-18 06:40:12
---

::: warning Requirement
After completing [Installation](/installation-instructions.html) of vuefull-generator, the following can be run
:::

### Generate new API + UI
Run the command **`yo vuefull book`** which will auto generate the following files. Where book is the model name. It will generate the 
- Database model named book
- API end point /api/books with GET,POST,PUT,DELETE,EXPORT routes
- Client routes for list, edit
- Add the client route to the leftmenu + dashboard

``` bash
vuefull-api/server/api/book/config.ts
vuefull-api/server/api/book/controller.ts
vuefull-api/server/api/book/index.ts
vuefull-api/server/api/book/model.ts
vuefull-api/server/routes.json

vuefull-client/pages/books/_id.vue
vuefull-client/pages/books/index.vue
vuefull-client/pages/books/config.js
vuefull-client/config/menu.json
```

### Config inside server api endpoint

::: warning path: <em>vuefull-api/server/api/book/config.ts</em>
 It defines the data types of each field. 
:::

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

Reference: <a href="https://docs.mongodb.com/manual/reference/bson-types/">https://docs.mongodb.com/manual/reference/bson-types/</a>

### Config inside a route

::: warning path: <em>vuefull-client/pages/books/config.js</em>
 Contains client settings in key value pair
:::

- api `Name of api e.g. books`
- heading `Header of that page`
-------
- fields
    - text `The title of the field`
    - value `The column/attribute name that the API respond with`
    - type `Type of data that attribute contains`

        It could be anything of 
        - text
        - number
        - select `Require options. e.g.
            {value: 'category', text: 'Category', type:'select', options: ['Fiction', 'Non fiction', 'Inspirational', 'Novel', 'Science', 'Story']}`
        - boolean
        - boolean-label
        - boolean-checkbox
        - currency
        - date
        - array
        - url 
        - detail
        - emailmask `Masks the field and displays only last 6 characters`
        - phonemask `Masks the field and displays only last 6 characters`

### More settings
The component named `List` accepts the following props
``` js
f: Array // fields
no: Object // List of actions to be removed from the listing page
api: String // API endpoint to be queried
heading: String // Heading of the listing page
```

e.g.
``` js
<list
      :f="[{ value: 'name', text: 'Title', type: 'text' }]"
      api="books"
      heading="Available Books"
      :no={clone:true,export:true,delete:true}
    ></list>
```

The above settings 
- Will list all books in database 
- have the heading as `Available Books`
- there will not be option for clone, export & delete