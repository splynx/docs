# Splynx site documentation

In this repository store documentation files for Splynx site.
After pushing to this repository, documentation in Splynx site will be automatically updated. 

### Files format description

#### Translations

Languages files should be placed in self directories.

![Language files example](./images/languages_files.png)

#### Page title

Each page should be begin from the page title.

```
Page Title
==========
```
This title will be show in the header of the documentation panel.

![Page title example](./images/page_title.png)

#### Image size

For set image size you can use url parameters.

```
![Image alt](http://site.com/images/img.png?w=200&h=100)
```

This code will be converted to:

```html
<img src="http://site.com/images/img.png?w=200&h=100" alt="Image alt" width="200" height="100">
```

#### Image src
For images `src` you can use absolute url or relative path.

Absolute url:

```
http://images.google.com/some_image.png
```

Relative path (recommended):

```
./images/my_image.png
```
