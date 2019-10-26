link: https://raw.githubusercontent.com/miguelmota/sass-cheatsheet/master/README.md


# Sass Cheatsheet

[http://sass-lang.com/](http://sass-lang.com/)

### Watching

```bash
sass --watch sass:css
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#using_sass)

### Comments

```css
// I will not show when compiled

/* I will be shown when compiled */
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#comments)

### Imports

```css
@import 'foo';
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#import)

### Variables

```css
$foo: #000 !default;
$bar: baz qux quux corge;
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#variables_)

### Nesting

Selector nesting

```css
.foo  {
  .bar {
    // .foo .bar { }
  }
}
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#nested_rules)

Property nesting

```css
.foo {
  text: {
    align: center; // .foo { text-align: center; }
  }
}
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#nested_properties)

### Parent Selectors

```css
a {
  &:hover {
    // a:hover { }
  }
}
```

```css
.bar {
 .foo & {
   // .foo .bar { }
  }
}
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#referencing_parent_selectors_)

### Interpolation

```css
$foo: bar;

.baz-#{$foo} {
  // .baz-bar { }
}
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#interpolation_)


### Concatenation

```css
$foo: 'serif';

.bar {
	$font: 'sans-' + $foo; // 'sans-serif'
}
```

### Mixins

```css
@mixin foo($bar, $baz: false) {
  color: $bar;
  @if baz {
    border-radius: $baz;
  }
}

.qux {
  @include foo(#000, 10px);
}
```

Variable arguments

```css
@mixin bar($baz...) {
  box-shadow: $baz
}

.qux {
  $baz: 0px 4px 5px #666, 2px 6px 10px #999;
  @include bar($baz);
}
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#defining_a_mixin)

### Extend

```css
%foo {
 color: #000;
}

.bar {
  background: #fff;
}

.baz {
  @extend %foo; // color: #000
  @extend %qux !optional; // fail silenty if not found
  @extend .bar; // background: #fff
}
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#extend)


### Control directives

#### if, if else, else

```css
$foo: bar;

.qux {
  @if $foo == bar {
     color: #000;
  } @else if $foo == baz {
    color: #fff;
   } @else {
     color: #999;
   }
}

.qux {
	color: if($foo == bar, #000, #999); // if([condition], [if true], [else])
}
```

```
$foo: "foo";
$bar: "bar";
$qux: "qux";

@if ($foo == "foo" and not ($bar == "bar")) or ($qux == "qux") {
  // second condition is true
}
```

#### each

```css
$foo: bar baz qux;

@each $f in $foo {
	.quux-#{$f} {
		background: url(quux-#{$f}.png); // .quux-bar { background: url(quux-bar.png) }
	}
}
```

#### for

```css
.qux {
	@for $i from 1 through 5 {
		&.qux-#{$i} {
			// .qux.qux-1 { }
		}
	}
}
```

#### while

```css
$i: 1;

.qux {
	@while $i <= 5 {
		&.qux-#{$i} {
			// .qux.qux-1 { }
		}

		$i: $i + 1;
	}
}
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#control_directives)


### Function directives

```css
@function foo($bar, $baz) {
	@return ($bar / $baz);
}

.qux {
	width: foo(10px, 2px); // 5px
}
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#functions)

### List functions

```css
$foo: bar baz qux quux;
$grault: garphly, waldo, fred, plugh;

length($foo); // 4 (index starts at 1)
append($foo, corge); // bar baz qux quux corge (does not alter original)
join($foo, $grault); // bar baz qux quux garphly, waldo, fred, plugh
index($foo, baz); // 2
nth($foo, 2); // baz
zip($foo, $grault); // [bar garphly] [baz waldo] [qux fred] [quux plugh]
```

`zip()` example

```css
$users: foo bar;
$colors: blue green;
$style: zip($names, $colors); // [foo blue] [bar green]
@each $u in $style {
  .users-#{nth($u, 1)} {      // .users-foo { }
    background: nth($u, 2);   // background: blue;
  }
 }
```

### Color functions

```css
$foo: #ff0000;

rgba($foo, 0.8); // rgba(0, 255, 0, 0.8)
lighten($foo, 20%); // #66ff66
darken($foo, 20%); // #009900
saturate($foo, 20%); // lime
desaturate($foo, 20%); // #19e619
mix(#ff0000, #0000ff); // #7f007f
mix(#ffff00, #0000ff, 20%); // #3300cc (3rd parameter is percentage of first color)
grayscale($foo); // grey
invert($foo); // magenta
complement($foo); // magenta
scale_color($foo, $lightness: 20%); // #33ff33
scale_color($foo, [$red], [$green], [$blue], [$saturation], [$lightness], [$alpha]); // changes color aspect(s) relative, rather than linearly, to the start value
```

[source](http://sass-lang.com/documentation/Sass/Script/Functions.html#rgb_functions)

### Number functions

```css
$foo: 1.4;
$bar: 1.3 4.5 -2.8;

round($foo;) // 1
ceil($foo); // 2
floor($foo); // 1
abs($foo); // 1.4
percentage($foo) // 140%
min($bar...) // -2.8
max($bar...) // 4.5
```

[source](http://sass-lang.com/documentation/Sass/Script/Functions.html#number_functions)

### Media queries

```css
.foo {
	@media (min-width: 768px) {
	  // @media (min-width: 768px) { .foo { } }
	}
}
```

Using a mixin

```css
@mixin respond-to($media) {
	@if $media == desktop {
		@media (min-width: 960px) {
			@content;
    	}
    } @else if $media == tablet {
    	@media (min-width: 768px) {
      		@content;
    	}
  	}
}

.foo {
	@inclue respond-to(tablet) {
		// @media (min-width: 768px) { .foo { } }
	}
}
```

[source](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#media)

#### Some helpful resources

- [Sass reference](http://sass-lang.com/documentation/file.SASS_REFERENCE.html)
- [The Sass Way](http://thesassway.com/)
- [Sasmeister](http://sassmeister.com/)
- [Scalable and Modular Architecture for CSS](http://smacss.com/)


### License

Released under the MIT License.


---
___


link: https://gist.github.com/AllThingsSmitty/3bcc79da563df756be46

##Sass Functions Cheat Sheet

1. [RGB Functions](#rgb-functions)
1. [HSL Functions](#hsl-functions)
1. [Opacity Functions](#opacity-functions)
1. [Other Color Functions](#other-color-functions)
1. [List Functions](#list-functions)
1. [Map Functions](#map-functions)
1. [Selector Functions](#selector-functions)
1. [String Functions](#string-functions)
1. [Number Functions](#number-functions)
1. [Introspection Functions](#introspection-functions)
1. [Miscel­laneous Functions](#miscellaneous-functions)

####RGB Functions

[**`rgb(­$red, $green, $blue)`**](http://sass-lang.com/documentation/Sass/Script/Functions.html#rgb-instance_method)
Creates a color from red, green, and blue values.

**`rgba­($red, $green, $blue, $alpha)`**
Creates a color from red, green, blue, and alpha values.

**`red(­$co­lor)`**
Gets the red component of a color.

**`gree­n($­col­or)`**
Gets the green component of a color.

**`blue­($c­olor)`**
Gets the blue component of a color.

**`mix(­$co­lor1, $color2, [$weig­ht])`**
Mixes two colors together.

==========
####HSL Functions

**`hsl(­$hue, $satur­ation, $light­ness)`**
Creates a color from hue, satura­tion, and lightness values.

**`hsla­($hue, $satur­ation, $light­ness, $alpha)`**
Creates a color from hue, satura­tion, lightness, and alpha values.

**`hue(­$co­lor)`**
Gets the hue component of a color.

**`satu­rat­ion­($c­olor)`**
Gets the saturation component of a color.

**`ligh­tne­ss(­$co­lor)`**
Gets the lightness component of a color.

**`adju­st-­hue­($c­olor, $degre­es)`**
Changes the hue of a color.

**`ligh­ten­($c­olor, $amount)`**
Makes a color lighter.

**`dark­en(­$color, $amount)`**
Makes a color darker.

**`satu­rat­e($­color, $amount)`**
Makes a color more saturated.

**`desa­tur­ate­($c­olor, $amount)`**
Makes a color less saturated.

**`gray­sca­le(­$co­lor)`**
Converts a color to grayscale.

**`comp­lem­ent­($c­olor)`**
Returns the complement of a color.

**`inve­rt(­$co­lor)`**
Returns the inverse of a color.

==========
####Opacity Functions

**`alph­a($­color) / opacit­y($­col­or)`**
Gets the alpha component (opacity) of a color.

**`rgba­($c­olor, $alpha)`**
Changes the alpha component for a color.

**`opac­ify­($c­olor, $amount) / fade-i­n($­color, $amount)`**
Makes a color more opaque.

**`tran­spa­ren­tiz­e($­color, $amount) / fade-o­ut(­$color, $amount)`**
Makes a color more transp­arent.

==========
####Other Color Functions

Visit [Sass Functions](http://sass-lang.com/documentation/Sass/Script/Functions.html).

==========
####List Functions

Visit [Sass Functions](http://sass-lang.com/documentation/Sass/Script/Functions.html).

==========
####Map Functions

Visit [Sass Functions](http://sass-lang.com/documentation/Sass/Script/Functions.html).

==========
####Selector Functions

**`sele­cto­r-n­est­($s­ele­cto­rs...)`**
Nests selector beneath one another like they would be nested in the styles­heet.

**`sele­cto­r-r­epl­ace­($s­ele­ctor, $original, $repla­cem­ent)`**
Replaces `$original` with `$repla­cement` within `$selector`.

More at [Sass Functions](http://sass-lang.com/documentation/Sass/Script/Functions.html).

==========
####String Functions

**`unqu­ote­($s­tri­ng)`**
Removes quotes from a string.

**`quot­e($­str­ing)`**
Adds quotes to a string.

**`str-­len­gth­($s­tri­ng)`**
Returns the number of characters in a string.

More at [Sass Functions](http://sass-lang.com/documentation/Sass/Script/Functions.html).

==========
####Number Functions

**`perc­ent­age­($n­umb­er)`**
Converts a unitless number to a percen­tage.

**`roun­d($­num­ber)`**
Rounds a number to the nearest whole number.

**`ceil­($n­umb­er)`**
Rounds a number up to the next whole number.

**`floo­r($­num­ber)`**
Rounds a number down to the previous whole number.

**`abs(­$nu­mber)`**
Returns the absolute value of a number.

**`min(­$nu­mbe­rs...)`**
Finds the minimum of several numbers.

**`max(­$nu­mbe­rs...)`**
Finds the maximum of several numbers.

**`rand­om(­[$l­imi­t])`**
Returns a random number.

==========
####Introspection Functions

**`feat­ure­-ex­ist­s($­fea­ture)`**
Returns whether a feature exists in the current Sass runtime.

**`vari­abl­e-e­xis­ts(­$na­me)`**
Returns whether a variable with the given name exists in the current scope.

**`glob­al-­var­iab­le-­exi­sts­($n­ame)`**
Returns whether a variable with the given name exists in the global scope.

**`func­tio­n-e­xis­ts(­$na­me)`**
Returns whether a function with the given name exists.

**`mixi­n-e­xis­ts(­$na­me)`**
Returns whether a mixin with the given name exists.

**`insp­ect­($v­alue)`**
Returns the string repres­ent­ation of a value as it would be repres­ented in Sass.

**`type­-of­($v­alue)`**
Returns the type of a value.

**`unit­($n­umb­er)`**
Returns the unit(s) associated with a number.

**`unit­les­s($­num­ber)`**
Returns whether a number has units.

**`comp­ara­ble­($n­umber1, $numbe­r2)`**
Returns whether two numbers can be added, subtra­cted, or compared.

**`call­($name, $args…)`**
Dynami­cally calls a Sass function.

==========
####Miscel­laneous Functions

**`if($­con­dition, $if-true, $if-fa­lse)`**
Returns one of two values, depending on whether or not `$condition` is true.

**`uniq­ue-­id()`**
Returns a unique CSS identi­fier.
