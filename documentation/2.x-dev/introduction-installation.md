---
layout: documentation
title: Introduction / Installation
---

This is the official documentation for Dwoo 2.0, oriented object PHP5 Template Engine for PHP.

If you have any exposure to other text-based template languages, such as Smarty you should feel right at home with Dwoo. It's both designer and developer friendly by sticking to PHP's principles and adding functionality useful for templating environments.

Dwoo is a templating system used to make creating websites easier and more structured.  
Developing with Dwoo can be broken up into two parts:
* Creating, initializing and managing the Dwoo runtime;
* Templating with the Dwoo templating language.

## A bit of history
Dwoo is a PHP5 Template Engine that was started in early 2008.  
The idea came from the fact that [Smarty](http://www.smarty.net/){:target="_blank"}, a well known template engine, is getting older and older.  
It carries the weight of it's age, having old features that are inconsistent compared to newer ones, being written for PHP4 its Object Oriented aspect doesn't take advantage of PHP5's more advanced features in the area, etc.  
Hence Dwoo was born, hoping to provide a more up to date and stronger engine.  
So far it has proven to be faster than Smarty in many areas, and it provides a compatibility layer to allow developers that have been using Smarty for years to switch their application over to Dwoo progressively.

##Prerequisites
Dwoo 2.0 embedded new features of PHP like Namespaces, so it need at least **PHP 5.3** to run.

##Installation

###Installing via Composer **(recommended)**
Dwoo is available on [packagist.org](https://packagist.org/packages/dwoo/dwoo){:target="_blank"} to do so, install [Composer](https://getcomposer.org/download/){:target="_blank"} and run the following command to get the latest version:
{% highlight bash %}
composer require dwoo/dwoo
{% endhighlight %}

###Installing from the PHAR release
1. Download the most recent tarball from the [downloads page](/downloads.html),
2. Move the PHAR somewhere in your project,
3. Go to the [PHAR archive section](#phar-archive) to know how to use PHAR and classes.

###Installing from the tarball release
1. Download the most recent tarball from the [downloads page](/downloads.html),
2. Unpack the tarball,
3. Move the files somewhere in your project,
4. Go to the [Basic section](#basic) to know how to use classes. 

##Usage
This section gives you a brief introduction for include and load Dwoo in your project.

###Basic
{% highlight php %}
<?php
// Include autoloader
require 'lib/Dwoo/Autoloader.php';

// Register Dwoo namespace and register autoloader
$autoloader = new Dwoo\Autoloader();
$autoloader->add('Dwoo', 'lib/Dwoo');
$autoloader->register(true);

// Create the controller, it is reusable and can render multiple templates
$dwoo = new Dwoo\Core();

// Create some data
$data = array('a'=>5, 'b'=>6);

// Output the result directly ... 
$dwoo->output('path/to/index.tpl', $data);
// ... or get it to use it somewhere else
$var = $dwoo->get('path/to/index.tpl', $data);
echo $var;
{% endhighlight %}

###Phar archive
This is the same example as above, using a Phar compile archive.
{% highlight php %}
<?php
// Include phar archive, not need to call autoloader anymore
require 'phar://dwoo.phar';

// Create the controller, it is reusable and can render multiple templates
$dwoo = new Dwoo\Core();

// Create some data
$data = array('a'=>5, 'b'=>6);

// Output the result directly ... 
$dwoo->output('path/to/index.tpl', $data);
// ... or get it to use it somewhere else
$var = $dwoo->get('path/to/index.tpl', $data);
echo $var;
{% endhighlight %}