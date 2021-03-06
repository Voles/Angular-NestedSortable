Angular UI NestedSortable
======================

An Angularjs ui component that can sort nested lists and bind data, and it dosen't need to depend on jQuery.


## Features

- Items can be sorted in their own list, moved across the tree, or nested under other items.
- It is possible to define elements that will not accept a new item/list
- Data binding. If you change the order, the data you bound will be updated.

## Usage

Angularjs script

```js
var app = angular.module('nestedSortableDemoApp', [
	'ui.nestedSortable'
]);
```  
Injecting `ui.nestedSortable` to your App.



HTML View or Templates
```html
<ol ui-nested-sortable="" ng-model="list">
  <li ng-repeat="item in list" ui-nested-sortable-item="">
    <div ui-nested-sortable-handle>
      {{item.title}}
    </div>
    <ol ui-nested-sortable="" ng-model="item.items">
      <li ng-repeat="subItem in item.items" ui-nested-sortable-item="">
        <div ui-nested-sortable-handle>
          {{subItem.title}}
        </div>
      </li>
    </ol>
  </li>      
</ol> 
```  

- Adding `ui-nested-sortable` to your root element.
- Using `ng-model` to bind the list data with element. It should be an array.
- Adding `ui-nested-sortable-item` to your item element, it always follow the `ng-repeat` attribute.
- Adding `ui-nested-sortable-handle` to mark which element do you want to handle the drage action
- All `ui-nested-sortable`, `ng-model`, `ui-nested-sortable-item` and `ui-nested-sortable-handle` are necessary. And they can be nested.
- If you add a `nodrag` attribute to an element, the element won't response for the drag action.


## Samples

### Sample 3

A nested recursive list, it binds with an unlimited nested array.  
[Try Sample3](http://jimliu.github.io/Angular-NestedSortable/demo/sample3.html)

### Sample 2

Two-level list, the data type of top level is 'chapter', the data type of the secend level is 'lecture', the node can only be dragged & dropped to another node which with same data type.  
[Try Sampl2](http://jimliu.github.io/Angular-NestedSortable/demo/sample2.html)

### Sample 1

A nested list, it binds with a nested array, if it's sort order is changed, the data will be updated.  
In this sample, it can only support 3-level nodes.
[Try Sample1](http://jimliu.github.io/Angular-NestedSortable/demo/sample1.html)

## ngmodules

[Give us a like on ngmodules](http://ngmodules.org/modules/Angular-NestedSortable)

## Development environment setup
#### Prerequisites

* [Node Package Manager](https://npmjs.org/) (NPM)
* [Git](http://git-scm.com/)

#### Dependencies

* [Grunt](http://gruntjs.com/) (task automation)
* [Bower](http://bower.io/) (package management)

#### Installation
Run the commands below in the project root directory.

#####1. Install Grunt and Bower

    $ sudo npm install -g grunt-cli bower
    
#####2. Install project dependencies

    $ npm install
    $ bower install

## Useful commands

####Test code
At the moment we only test with JSHint. Later on we can extend requirements for the source code and add real unit- and E22 tests.

    $ grunt jshint