# stylus-csswizardry-grids

This is a port of Harry Roberts' csswizardry-grids into **Stylus**.
It has all the functionality of the Sass version, with the following extra
features:

* `use_floats` (default `false`): However, setting this to `true` allows
  you to use `float: left` instead of `display: inline-block` for the grid's
  basic scaffolding. This alleviates some of the spacing issues inherent to
  `display: inline-block`; however, right-, center-, middle- and bottom-aligned
  grid layouts currently don't work with float mode.
* **Customization**: the grid class selectors are generated by interpolating
  a small number of variables. Tweaking class names, e.g. shortening `.grid`
  to `.gr` and `.grid__item` to `.g`, is now very easy to accomplish by
  editing those variables.

Also, a few formerly missing features have been added back:

* `use_silent_classes` (default `false`): This settings allows you to
  completely eschew grid classes from your markup, and use the grid via
  `@extend`. When `true`, only those classes that you actually `@extend`
  in your stylesheets will be generated, shaving a few kilobytes off the
  size of the compiled CSS.
* `use_markup_fix` (default `true`): leaves fixing the spacing issues that are
  inherent to `display: inline-block` up to you - e.g. by eliminating
  whitespace from your markup (hence the name), or by setting `font-size: 0`
  on the grid container. When this variable is set to `false`, an empirically
  determined fix is applied. It gives small negative values to the properties
  `letter-spacing` and `word-spacing`, which effectively fixes the spacing
  issue across browsers. It is, however, not guaranteed to be bulletproof.
  This setting does nothing if `use_floats` is true.

**Simple, fluid, nestable, flexible, Stylus-based, responsive grid system.**

* Fully responsive
* Infinitely nestable
* Endless possible combinations
* Simple to understand, human-friendly classes
* Option to keep classes out of your HTML
* Robust
* Simple
* No `.clear` or `.last` classes
* It just _works_

Please see [Responsive grid systems; a solution?](http://csswizardry.com/2013/02/responsive-grid-systems-a-solution/)
for a comprehensive overview of the principles of the grid system.

## Setup

Simply fill in/adjust the relevant variables.

* `$gutter` controls how much space there is between columns.
* `$lap-start` and `$desk-start` tell csswizardry-grids when to fire particular
  media queries to service those particular sizes. Note that csswizardry-grids
  works out the ends of any other breakpoints by using these numbers.

## Basic usage

If you are using traditional classes then an example, basic usage might look
like this:

    <div class="grid">

        <div class="grid__item  lap-one-half  desk-two-thirds">
            ...
        </div>

        <div class="grid__item  lap-one-half  desk-one-third">
            ...
        </div>

    </div>

There is a very simple demo which can be found at
[csswizardry.github.com/csswizardry-grids](http://csswizardry.github.com/csswizardry-grids).
