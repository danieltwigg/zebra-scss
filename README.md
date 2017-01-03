# Zebra - a CSS grid system without the fluff
This is a grid system at it's rawest. Zebra simply provides you with a number of premade CSS classes which you can use to quickly add structure to a website.

## Getting started
It's really easy to get started with Zebra, just create an element with the class of `row`, and then add your columns within.

```css
<div class="row">
	<div class="col--1of6">A column that spans 1/6 of the parent</div>
	<div class="col--3of6">A column that spans 1/2 of the parent</div>
	<div class="col--2of6">A column that spans 1/3 of the parent</div>
</div>
```

## What is Zebra?
Based on the BEM methodology.

Base columns follow a slightly simplified version of the BEM methodology, combining the properties of `.col` (a block) with it's size `.col--(1-12)of(1-12)` (a modifier). This is done for a couple of reasons; 
1. Firstly, there should never be an instance where a column element doesn't have a size modifer, as this would result in a column with no fixed width.
2. Secondly, this helps to keep the DOM cleaner, as there are less classes littering each element.

```css
<div class="col--1of2">Zebra's simplified column classes</div>
<div class="col col--1of2">Typical BEM usage</div>
```

## Usage examples
```css
<div class="row row--flex">
	<div class="col--1of6">This column will be taller than the rest due to extra content</div>
	<div class="col--3of6">Lorem ipsum dolor sit amet</div>
	<div class="col--2of6">Lorem ipsum dolor sit amet</div>
</div>
```

Blank rows will automatically keep their width, as there are no floats used.

```css
<div class="row">
	<div class="col--1of6"></div>
	<div class="col--3of6">This column starts 1/6 of the way across the row</div>
	<div class="col--2of6">Lorem ipsum dolor sit amet</div>
</div>
```

## Settings
These settings variables are all stored at the top of the zebra.scss and can be modified for your project.

| Setting         | Type    | Default     | Description |
|-----------------|---------|-------------|-------------|
| $site-width     | string  | 1400px      | The max width of your site, used in the `row--contained` class. |
| $columns        | list    | 2, 3, 4, 12 | Each number represents the number of columns that a row will be split into. |
| $enable-offset  | boolean | true        | Enable the generation of column offset classes. |
| $enable-push    | boolean | false       | Enable the generation of column push classes. |
| $enable-pull    | boolean | false       | Enable the generation of column pull classes. |

Whilst websites from the early days of the web were often restricted to using a 960px grid and tables, current technology allows designers and developers infinitely more freedom when it comes to structuring a page.

This results in designs that no longer follow a set grid, with elements often containing their own grid

Just like a Zebra's stripes, every website is unique.


Whilst most modern grid systems are implementing more and more advanced features, Zebra is taking a more stripped back approach. You won't find set column gutters or margins, and there are only a few column sizes that have responsive behaviour built in by default.

