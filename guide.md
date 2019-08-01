---
title: Usage Instructions (Guide)
date: 2019-06-18 06:40:12
---
Config inside a route
`/pages/books/config.js`

It contains key value pair

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
        - emailmask `Masks the field and displays only last 4 characters`
        - phonemask `Masks the field and displays only last 4 characters`
