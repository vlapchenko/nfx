# NFX Wave.js
Java Script Client Library

## General-Purpose Functions

### [Array functions](ArrayFunctions.md)

### Operations with objects and functions

##### clone(object obj): object
Deep clones data object (not functions).

##### extend(object obj, object ext, bool keepExisting): object
Mixin behavior - extends `obj` with properties of `ext`.
If flag `keepExisting=true` then existing object key is preserved, even if it is null.

##### isArray(object obj): bool
Returns true when the passed parameter is an array, not a map or function.

##### isFunction(object obj): bool
Returns true when the passed parameter is a function, not a map object or an array.

##### isMapOrArray(obj): bool
Returns true when the passed parameter is an array, or map but not a function.

##### isObject(object obj): bool
Returns true when the passed parameter is a map, not an array or function.

##### isSame(object obj1, object obj2): bool
Returns true if both objects represent the same scalar value or complex structure/map that is keys/values of maps/arrays. Nulls are considered equivalent.

##### overrideFunction(function original, function fn): function
Overrides existing function by wrapping in new one. May call base like so:
```js
object.about = WAVE.overrideFun(object.about, function(){ return this.baseFunction() + "overridden" });
```

##### propStrAsObject(object obj, string prop)
Checks object property for string value and if it is then converts it to object (map).
Does nothing if prop does not exist, is null or not a string value.
```js
var o1 = {a: 1, b: '{"c": "yes", "d": "no"}'};
// WAVE.isObject(o1.b)) = false

WAVE.propStrAsObject(o1, "b");
// WAVE.isObject(o1.b)) = true
```
    
### [String functions](StringFunctions.md)

##### Checking types
Returns true if `tp` is in:
* **isObjectType(tp)** - ["object", "json", "map", "array"]
* **isIntType(tp)** - ["int", "integer"]
* **isRealType(tp)** - ["float", "real", "double", "money"]
* **isBoolType(tp)** - ["bool", "boolean", "logical"]
* **isStringType(tp)** - ["str", "string", "char[]", "char", "varchar", "text"]
* **isDateType(tp)** - ["date", "datetime", "time", "timestamp"]

##### convertScalarType(bool nullable, value, string type, dflt)
Converts scalar value into the specified type:
```js
var v;
v = convertScalarType(false, 13, "string", "<unconvertible>"); // v = '13'
v = convertScalarType(true, "13", "int");       // v = 13
v = convertScalarType(false, "abc", "int", 10); // v = 10
```

### Events
[WAVE.EventManager](EventManager.md) mixin implements the event-handler mechanism and can be added to any class.

### Unit testing
Unit testing concept is represented by [WAVE.UTest](UTest.md) static class.


## Record Model
Record model is in the WAVE.RecordModel namespace.

### Classes
* [Record](Record.md)
* [Field](Field.md)
* [RecordView](RecordView.md)


