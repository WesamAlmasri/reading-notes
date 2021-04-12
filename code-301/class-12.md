# Components

![ejs templating image](https://miro.medium.com/max/3920/1*VMI-NGFtYwWM7aBoKOg72Q.jpeg)

## EJS Partials

### Partials

Partials are templates that we can write, that we can include in other templates. For example our html boilerplate, we don’t want to include on every template, that’s not very DRY.

### Partials File Structure

![partials file structure image](https://camo.githubusercontent.com/eacea61e061a25057938351b14fd0e6fbb11ee02c61021a60d6cdb05ff7beef7/68747470733a2f2f6e636f7567686c696e2e636f6d2f7374617469632f33326133396466663032666230663964343164666139393061326439353062352f38353961662f332e706e67)

Because partials are still templates, we are going to include them in the views folder, in their own sub-directory.

### header.ejs

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>EJS App</title>
    <link rel="stylesheet" type="text/css" href="/app.css"
</head>
<body>
```

### footer.ejs

```html
</body>
</html>
```

### Linking Partials in Templates

`<% include templateName %>`

This new command `include` is telling Express to pull the contents of the named template and place it in place of this command.

`<%- include("partials/header.ejs") %>`
