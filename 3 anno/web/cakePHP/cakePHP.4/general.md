Before starting you should make sure that you have got an up to date PHP version:

```php
php -v
```

# DB
Defining relations between different objects in your application should be a natural process. For example, an article may have many comments, and belong to an author. Authors may have many articles and comments. The four association types in CakePHP are: hasOne, hasMany, belongsTo, and belongsToMany.

| Relationship  | Association Type | Example                             |
|---------------|------------------|-------------------------------------|
| one to one    | hasOne           | A user has one profile.             |
| one to many   | hasMany          | A user can have multiple articles.  |
| many to one   | belongsTo        | Many articles belong to a user.    |
| many to many  | belongsToMany    | Tags belong to many articles.       |

# View 

## Extending views
View extending allows you to wrap one view in another.Combining this with view blocks gives you a powerful way to keep your views DRY.


```php
<!-- templates/Common/view.php -->
<!-- Used as PARENT VIEW -->
<h1><?= h($this->fetch('title')) ?></h1>
<?= $this->fetch('content') ?>

<div class="actions">
    <h3>Related actions</h3>
    <ul>
    <?= $this->fetch('sidebar') ?>
    </ul>
</div>
```


```php
<!-- templates/Posts/view.php -->
<?php
//extend the common view and populate it
$this->extend('/Common/view');

$this->assign('title', $post->title);

//inside this block it renders the custom view for sidebar

$this->start('sidebar');   
?>
<li>
<?php
echo $this->Html->link('edit', [
    'action' => 'edit',
    $post->id,
]);
?>
</li>
<?php $this->end(); ?>

// The remaining content will be available as the 'content' block
// In the parent view.
<?= h($post->body) ?>
```

**NOTE**

multiples extends calls are overridden.

```php
$this->extend('/Common/view');
$this->extend('/Common/index');
```
The above will result in /Common/index.php being rendered as the parent view to the current 

## Extending layouts

also layouts can be extendeds.
For example if we wanted to wrap a block with additional markup you could do:

```php
// Our layout extends the application layout.
$this->extend('application');
//prepend add some code at the beginning of an existing block, without removing the code
$this->prepend('content', '<main class="nosidebar">');
$this->append('content', '</main>');

// Output more markup.

// Remember to echo the contents of the previous layout.
echo $this->fetch('content');
```

## Using view block
View blocks provide a flexible API that allows you to define slots or blocks in your views/layouts that will be defined elsewhere. For example, blocks are ideal for implementing things such as sidebars, or regions to load assets at the bottom/top of the layout.

```php
// Create the sidebar block.
$this->start('sidebar');
echo $this->element('sidebar/recent_topics');
echo $this->element('sidebar/recent_comments');
$this->end();

// Append into the sidebar later on. and add popular topics
$this->start('sidebar');
echo $this->fetch('sidebar');
echo $this->element('sidebar/popular_topics');
$this->end();
```

you can also append into a block usinf `append()`:

```php
$this->append('sidebar');
echo $this->element('sidebar/popular_topics');
$this->end();

// The same as the above.
$this->append('sidebar', $this->element('sidebar/popular_topics'));
```

to clear a block:

```php
// Clear the previous content from the sidebar block.
$this->reset('sidebar');

// Assigning an empty string will also clear the sidebar block.
$this->assign('sidebar', '');
```

assing a block's content is usefull when we want to convert view variable into block:

```php
// In view file or layout above $this->fetch('title')
$this->assign('title', $title);
``` 

prepend append at the beginning, and append append at the end.

## Display block

using `fetch()`. `fetch()` return '' if a block doesn't exist
```php
<?= $this->fetch('sidebar') ?>
```

You can also use fetch to conditionally show content that should surround a block should it exist. This is helpful in layouts, or extended views where you want to conditionally show headings or other markup:

```php
// In templates/layout/default.php
<?php if ($this->fetch('menu')): ?>
<div class="menu">
    <h3>Menu options</h3>
    <?= $this->fetch('menu') ?>
</div>
<?php endif; ?>
```
You can privide a default value.
```php
<div class="shopping-cart">
    <h3>Your Cart</h3>
    <?= $this->fetch('cart', 'Your cart is empty') ?>
</div>
```


## Block for script and css file

You can add css and script in every view without modifying the layout.

```php
<?php
// In your view file
$this->Html->script('carousel', ['block' => true]);   // add one script to  'script' block.
$this->Html->css('carousel', ['block' => true]);
?> // add one script to  'css' block.

// In your layout file.
<!DOCTYPE html>
<html lang="en">
    <head>
    <title><?= h($this->fetch('title')) ?></title>
    <?= $this->fetch('script') ?> //fetch script block defined in the view
    <?= $this->fetch('css') ?>
    </head>
    // Rest of the layout follows

// OUTPUT :
<script src="/js/carousel.js"></script>
<link rel="stylesheet" href="/css/carousel.css" />
```

The Cake\View\Helper\HtmlHelper also allows you to control which block the scripts and CSS go to:

```php
// In your view
$this->Html->script('carousel', ['block' => 'scriptBottom']);

// In your layout
<?= $this->fetch('scriptBottom') ?>
```

## Layouts
