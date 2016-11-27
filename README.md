# CS 100 - Lab 3: Composite and Strategy Patterns

## Composite Pattern
You will start this lab by creating a composite pattern for representing an expression tree. The first expression to be executed (in this case, 7 * 4) will be at the deepest level. The result of that calculation then becomes an input to the addition (which becomes 3 + 28), and that result becomes an input to the subtraction (31 - 2). The tree is evaluated recursively from the bottom to the top, and is constructed in this particular way because of the order of operations.

You will write a composite pattern for representing these expression trees. You are required to use the following base class:

```class   Base  {
    public:
        /* Constructors */
        Base() { };
        /* Pure Virtual Functions */
        virtual double evaluate() = 0;
    };
```

Note that the main function in the base class is `evaluate()`, which will be used to return the value of the tree.

You will have one type of leaf node which will represent a number (`class Op`), and two types of composite nodes. There will be four types of nodes that have two children, capable of expressing the operations multiply (`class Mult`), divide (`class Div`), add (`class Add`), and subtract (`class Sub`). There also be one type of node that only has one child, which expresses squaring a value (`class Sqr`). Notice that any parentheses that would be in the expression can be implemented in the trees structure rather than explicitly with a node.

You are not required to implement functionality for parsing an expression, but can build the trees by instantiating nodes individually and adding them as children. You should fully test your system by creating expression trees of different sizes and compositions.

## Strategy Pattern
Now that you have created your expression tree classes, we will create a strategy pattern for sorting these trees by their `evaluate()` value. You will start this by creating two containers, one that uses a vector to hold your trees (`class VectorContainer`), and one that uses a list (`class ListContainer`). Both of these classes hold the top node pointers of the trees, so the list or vector would be of the type `<Base*>`.

You will also implement two sort functions for sorting these containers, one that uses the selection sort algorithm  and one that uses the  bubble sort algorithm  (you may directly adapt this code when writing your sort functions).

Notice that your container class requires a reference to your sorting class (and vice-versa). This will require you to use forward declarations and object file compilation. The easiest way to compile with object files (without learning more specific g++ commands) is to use the makefile I have provided you with.
