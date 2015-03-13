_Full Documentaion for Class templater as of version 0.2.1, and typographical horror._


#  #
# ATTRIBUTES #

## filename: string ##
Holds the path to the template file.

Set
  * via instantiation: templater(string $file) or
  * via setfile(string $file)


## filestring: string ##
Holds the template string from file or direct input.

Set
  * via instantiation: templater(string $file) if $file is set or
  * via setfile(string $file) if $file is set or
  * via setfilestring(string $template)



## cons: array ##
Holds the keys and corresponding values for conditional tags in an associative array.

Set
  * via addcons(string $varname, bool $condition) or
  * via setcons(array $conditionals)



## vars: array ##
Holds the keys and corresponding values for single data variables in an associative array.

Set
  * via addvars(string $varname, string $value)
  * via setvars(array $variables)



## loops: array ##
Holds row data in an array of associative arrays, keys of assoc arrays are tags inside the loop.

Set
  * via addloops(string $loopname, array $row)
  * via setloops(array $loops)



---

#  #
# public METHODS #



## public function templater(string $filename): constructor ##
**Description**
  * Sets _attribute string filename_.
  * Also if _parameter $filename_ is a non-empty string, then contents of the file specified in this parameter is read as a string and stored in _attribute filestring_.

**Parameters**
  * string $filename: should be a relative path to the template file from the instantiation.

**Returns** nothing

_I avoided using construct() in concern of our PHP4 friends._



## pubic function setfile(string $filename) ##
**Description**
  * An alias for constructor templater(string $filename)

Note: this will overwrite attribute filename and filestring.



## public function setfilestring(string $filestring) ##
**Description**
  * Sets _attribute string filename_

**Parameters**
  * string $filestring: a string that may contain template tags

**Returns** nothing

Note: this will overwrite attribute filestring.



## public function addvar(string $varname, string $data) ##
**Description**
  * Adds a single variable to _attribute array vars_ with key as $varname and corresponding string value as $data

**Parameters**
  * string $varname will be the key/index
  * string $data will be the corresponding value

**Returns** nothing



## public function addcon(string $varname, bool $data) ##
**Description**
  * Adds a boolean variable to _attribute array cons_ with key as $varname and corresponding boolean value as $data

**Parameters**
  * string $varname will be the key/index
  * string $data will be the corresponding boolean value

**Returns** nothing



## public function addloop(string $varname, array $data) ##
**Description**
  * Adds an array to _attribute array loops_ with key as $varname and corresponding arrays as $data

**Parameters**
  * string $varname will be the key/index
  * string $data will be the corresponding arrays

**Returns** nothing



## public function setvars(array $data) ##
**Description**
  * Sets or overwrites the _attribute array vars_ with array $data, reminder: this will overwrite the existing _attribute array vars_ with $data.

**Parameters**
  * array $data should be an associative array, keys are tags in the expected template, values can be anything except arrays or objects

**Returns** nothing



## public function setcons(array $data) ##
**Description**
  * Sets or overwrites the _attribute array cons_ with array $data, reminder: this will overwrite the existing _attribute array cons_ with $data.

**Parameters**
  * array $data should be an associative array, keys are tags in the expected template, values should be boolean

**Returns** nothing



## public function setloops(array $data) ##
**Description**
  * Sets or overwrites the _attribute array loops_ with array $data, reminder: this will overwrite the existing _attribute array loops_ with $data.

**Parameters**
  * array $data should be an associative array of associative arrays, higher level keys are names of the loop tags in the template, while lower level keys are names of the tags inside the loop tags

**Returns** nothing



## public string function render() ##
**Description**
  * Returns the parsed template file.

**Parameters** none

**Returns**
  * A string of the parsed template file.



---

#  #
# private METHODS #


## private function parsecons(string $filestring) ##
**Description**
  * Searches for conditional tag blocks in $filestring and replaces them with the corresponding values defined in _attribute array cons_.

**Parameters**
  * string $filestring a string that contains conditional tag blocks.

**Returns**
  * a string wherein the conditional tag blocks are parsed



## private function parsevars(string $filestring) ##
**Description**
  * Searches for single tags in $filestring and replaces them with the corresponding vaues defined in _attribute array vars_.

**Parameters**
  * string $filestring a string that contains single tags.

**Returns**
  * a string wherein the single tags are parsed.



## private function parseloops(string $filestring) ##
**Description**
  * Searches for loop tag blocks in $filestring and replaces them with the corresponding values defined in _attribute array loops_.

**Parameters**
  * string $filestring a string that contains loop tag blocks.

**Returns**
  * a string wherein the loop tag blocks are parsed


