Objective:
The goal of this project is to build a syntax checker that validates nested function calls in a
simple programming language. The syntax checker will ensure that function calls are
properly nested and that arguments passed in each function call are valid.
Project Scope:
1. Function Declaration: Functions are declared with a return type, function name,
parameters, and body. The syntax checker will ensure that functions are properly defined
and invoked.
2. Nested Function Calls: The syntax checker will validate that nested function calls (e.g.,
f(g(h(x))) ) are syntactically correct.
3. Parameter Validation: The syntax checker will ensure that the arguments passed to each
function match the expected types and number of parameters.
Example of Input Program:
int f(int a) {
return a + 1;
}
int g(int b) {
return f(b) * 2;
}
int h(int c) {
return g(f(c));
}
int result = h(5);
Grammar Definition:
Here is a context-free grammar (CFG) that describes the syntax for nested function calls,
function declarations, and function invocation.
Grammar Rules:
Program -> FunctionDecl FunctionCall
FunctionDecl -> ReturnType FunctionName '(' ParamList ')' Block
ReturnType -> 'int' | 'float' | 'void'
ParamList -> Param | Param ',' ParamList | ε
Param -> Type 'var'
Type -> 'int' | 'float'
Block -> '{' StmtList '}'
StmtList -> Stmt | Stmt StmtList
Stmt -> Assign | FunctionCall
Assign -> 'var' '=' Expr ';'
Expr -> 'var' | 'num' | FunctionCall
FunctionCall -> FunctionName '(' ArgList ')' ';'
ArgList -> Expr | Expr ',' ArgList | ε
FunctionName -> 'var'
Breakdown of Grammar:
1. Program: A program consists of function declarations and function calls.
2. FunctionDecl: Represents a function declaration, which includes the function name,
parameters, return type, and function body.
3. ReturnType: Specifies the type returned by the function (e.g., int, float, void).
4. ParamList: Represents a list of parameters for a function.
5. FunctionCall: Represents calling a function, which can include other nested function calls
as arguments.
6. ArgList: Represents a list of arguments passed to a function, which may include nested
function calls.
List of Terminals:
1. Keywords:
o int
o float
o void
2. Operators:
o = (assignment operator)
o , (comma to separate parameters or arguments)
o +, * (arithmetic operators)
3. Punctuation:
o {, } (braces for blocks of code)
o (, ) (parentheses for function parameters and function calls)
o ; (statement terminator)
4. Literals:
o Identifiers (for variable names and function names): represented as var,
FunctionName.
o Numeric literals: represented as num (for integers and floating-point
numbers).
List of Non-Terminals (Variables):
1. Program: Represents the entire program, which consists of function declarations
and function calls.
2. FunctionDecl: Represents a function declaration, which includes the function name,
return type, parameters, and body enclosed in {}.
3. ReturnType: Represents the type that the function returns, such as int, float, or
void.
4. ParamList: Represents the list of parameters for a function, which can be empty or
contain multiple parameters.
5. Param: Represents a single parameter, consisting of its type and variable name.
6. Type: Represents the data type of a parameter (e.g., int, float).
7. Block: Represents the body of the function, which contains a list of statements.
8. StmtList: Represents a list of statements inside a block.
9. Stmt: Represents a single statement, which can be an assignment or a function call.
10. Assign: Represents an assignment statement (e.g., var = Expr;).
11. Expr: Represents an expression, which can be a variable, a number, or a nested
function call.
12. FunctionCall: Represents a function call, where the function is invoked with
arguments (which can be other nested function calls).
13. ArgList: Represents a list of arguments passed to a function. This can include other
function calls as arguments.
14. FunctionName: Represents the name of the function being called.
