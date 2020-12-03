# Visitor Pattern

> Author: Brian Crites ([@brrcrites](https://github.com/brrcrites))


## Iterator Class

* Iterator: this is the base class for defining the interface for all the other iterator classes
* NullIterator: this iterator is created by expression tree classes which have no children to iterate over such as the operands
* BinaryIterator: this iterator is created by expression tree classes with two children, such as operators, and returns one of the children per iteration
* PreorderIterator: this iterator is created by a user to traverse an entire expression tree. Note that it will skip the first node in the expression tree so its helpful to add a "dummy" node as root which will be skipped

## The Visitor Class


## Modifying the Expression Tree Elements

In addition to completing the functionality for the above visitor class, you will also need to modify all the classes that can exist in an expression tree to allow for the `CountVisitor` to access them. You should add the function `void accept(CountVisitor*)` to the necessary classes which will then call the appropriate function within the `CountVisitor`.

Once you have implemented this function and created the `CountVisitor` class you will need to create a number of unit tests to verify that your visitor paired with your iterator can correctly count all the nodes in various expression trees. Remember that the preorder iterator will skip the root node, so you should add a "dummy" node (any operator) to your tree and make sure to account for this in your unit tests.
