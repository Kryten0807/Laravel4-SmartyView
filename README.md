Smarty for Laravel 4
====================

Very hacky implementation of Smarty for Laravel 4.

Unlike Twig and basically anything besides raw PHP and Blade, this mostly supports View Composers (at least when the events are used to define variables and when smarty {extends} or {include} tags are used).

Undefined variables (and other E_NOTICE errors) are also silently allowed, as a matter of personal preference.

Smarty itself has been included because file edits were required for View Composer support. It should not be upgraded without these being merged, unless you don't care about View Composers.

Installation
----------------

You can install this through composer with:

	"dark/smarty-view": "dev-master"
	
in composer.json -> "require".

Usage
----------

To use, add to config/app.php -> providers:

	'Dark\SmartyView\SmartyViewServiceProvider',
	
Then simply reference templates using the normal dot syntax of Laravel. 

For example to load smarty template ``views/blog/post.tpl``, you would use ``View::make('blog.post')``. In Smarty {include} or {extends} tags, you should continue to use the full directory syntax, e.g. ``{extends file="blog/post.tpl"}``.