### @ 0.2.6 ###
  * fixed a bug wherein the templater removes most of your inline css and javascript.

### @ 0.2.3 ###
  * corrected default render rule to `parse all remove all`.
  * added a none keyword to the render rules.

### @ 0.2.2 ###
  * corrected parsecons, it was accepting empty and true both as true values.
  * added a remove feature for undefined tags.
  * rendering files now has rules, see [user guide](UserGuide.md) for more info.

### @ 0.2.1 ###
  * You can now set a string instead of reading from a template file. a `setfilestring` method is now available. _[see user guide for more info](UserGuide.md)_
  * an alias for constructor is now available as `setfile()`
  * you can now instantiate without a parameter (`$page = new templater()`)
  * yes, i know that it has only been 3+ hours since release 0.2

### @ 0.2 ###
  * More encapsulation, yey!
  * Tag identifiers for vars are no longer set on creation
  * methods `setvars`, `setloops` and `setcons` are now available again, 'coz now they made sense to be there again.

### @ 0.1.3 ###
  * Added a conditional tag feature, `{con:var}conditional phrase{/con:var}`. _[see user guide for more info](UserGuide.md)_
  * Removed `setvars` and `setloops` temporarily, it made no sense to be there.

### @ 0.1.2 ###
  * Made `render()` handle empty arrays of vars and loops.

### @ 0.1.1 ###
  * Cleaned some bugs.

### @ 0.1 ###
  * RELEASED. oh yeah.