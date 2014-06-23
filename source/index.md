---
title: API Reference

language_tabs:
  - javascript

toc_footers:
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

By using existing frameworks like jQuery, MooTools, AngularJS, etc., we obtain very comprehensive frameworks, but they are way too large. The objective of jayScript is to provide a set of features without extending any internal object, keeping the framework light in space, but also in processing time.

Inspired by frameworks like underscorejs that establishes a list of useful programming functions, jayScript has come to life, having not only a list of functions that assist in the development, but also, element selectors and other features.


# Downloads

<a href='http://jayscript.servehttp.com/static/js/jayScript.js'>Development Version (0.9), Uncompressed</a>

<a href='http://jayscript.servehttp.com/static/js/jayScript.min.js.gz'>Production Version (0.9), Minified and Gzipped</a>

# Function list

## forEach

`j.forEach(list, iterator, [scope])`

Runs through a list of elements by invoking the iterator function for each of them. This function is linked to the scope object, if any are defined. Each invocation of the iterator is made with three arguments: (element, index, list). If the list is a Javascript object, then the iterator arguments will be (value, key, list). ForEach returns the native function if it exists, and returns the original list at the end.

> Array example:

```javascript
j.forEach([1, 2, 3], function(entry, index, list){
  console.log(entry);
  console.log(index);
  console.log(list);
});
```

> Object example:

```javascript
j.forEach({foo: 1, bar: 2}, function(val, key, obj){
  console.log(val);
  console.log(key);
  console.log(obj);
});
```

## trim

`j.trim(string)`

Returns a string with whitespaces cleaned on both sides. The trim function does not affect the initial string value.

```javascript
var trimedString = j.trim("   foo   ");
- trimedString = "foo"
```

## trimLeft

`j.trimLeft(string)`

Returns a string with whitespaces cleaned on the left side. The TrimLeft function does not affect the initial string value.

```javascript
var trimedString = j.trimLeft("   foo   ");
- trimedString = "foo   "
```

## trimRight

`j.trimRight(string)`

Returns a string with whitespaces cleaned on the right side. The trimRight function does not affect the initial string value.

```javascript
var trimedString = j.trimRight("   foo   ");
- trimedString = "   foo"
```

## stringContains

`j.stringContains(string, content)`

Returns true or false if a string exists within another string.

```javascript
var contains = j.stringContains("foobar", "foo");
- contains = true
```

## keys

`j.keys(object)`

Returns all property names of the object.

```javascript
var keys = j.keys({foo: 1, bar: 2});
- keys = ["foo", "bar"]
```

## isObject

`j.isObject(value)`

Returns true if the value is an object. Notice that JavaScript arrays and functions are objects while strings and numbers are not.

```javascript
var foo = j.isObject({});
- foo = true

var foo = j.isObject(1);
- foo = false
```

## loadFile

`j.loadFile(files, callback)`

Asynchronous loader of JavaScript and css files. The first parameter must be an array of objects, each object corresponds to a file to be imported.

Object structure:

* fileName: name of the file.
* fileType: type of the file (js or css).

```javascript
j.loadFile([
    {fileName:'foo.css',fileType:'css'},
    {fileName:'jquery.js',fileType:'js'}
  ],function(){
    console.log("loaded");
  }
);
```

## checkIfFileLoaded

`j.checkIfFileLoaded(filename, filetype)`

Checks the html tag for the desired file has already been inserted.

```javascript
console.log(j.checkIfFileLoaded('foo.css','css'));
```

## onPageLoaded

`j.onPageLoaded(callback)`

Executes a callback function after the page is read, including all images, frames and objects.

```javascript
j.onPageLoaded(function () {
  console.log("page loaded");
});
```