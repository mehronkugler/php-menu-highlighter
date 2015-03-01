# php-menu-highlighter

PHP Menu Highlighter - highlight current page in your navigation menu.

This uses the nth-child(x) property of CSS to target menu item # x, where x is your navigation menu item in an array. Let's say you have the following menu:

```html
<ul class="navigation">
  <li>Home</li>
  <li>About</li>
  <li>News</li>
</ul>
````

In PHP you set up an array, like so:
```php
$menuitems = [
  "home" => 1,
  "about" => 2,
  "news" => 3,
  ]
```

And now that numbers are assigned to each navigation menu item, we can specifically target each menu item using li:nth-child and override its style with inline CSS.

Create our PHP function, we'll call it "highlight":
```php
<?php
  function highlight($index)
  {
    $menuitems = [
    "home" => 1,
    "about" => 2,
    "news" => 3,
    ];

    echo "
      <style>
        ul.navigation > li:nth-child(" . $menuitems[$index] . ") {
        background-color: #B8C7CF;
        }
      </style>
    ";
  }
?>
```
Save this to "highlight.php"

Then use the function on each page. For example, in the "home.php" page, we would use the PHP function like this:

```php
<?php include 'highlight.php' ?>
<?php highlight("home") ?>
```

And this will use CSS to highlight the menu item by way of PHP.
