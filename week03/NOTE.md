# 每周总结可以写在这里
表达式
表达式有基础表达式 PrimaryExpression，下面四种方式都是 PrimaryExpression 的范畴

string、number、null、布尔值
函数、类、数组、正则等特殊对象类型
thish 或者变量
加上圆括号的任何表达式
MemberExpression 就是由 PrimaryExpression 表达式组成的。它通常是用于访问对象成员的。

a.b
a['b']
new.target
super.b
NewExpression

MemberExpression 加上 new 就是 NewExpression
CallExpression

在 Member Expression 里面加上一个括号的参数列表，或者用 super 关键字
a.b(c)
super()
LeftHandSideExpression 左值表达式

NewExpression 和 CallExpression 统称为左值表达式
RightHandSideExpression 右值表达式

对于右值表达式来说，它是以左值表达式为最小单位开始构成，也就是说左值表达式是右值表达式的基础。
转换类型
关于转换类型，js 中有隐式转换，还有类型装箱和拆箱的过程。
语句
语句分为简单语句和复合语句

简单语句
ExpressionStatement ( a = 1 + 2 )
EmptyStatement ( ; )
DebuggerStatement ( debugger )
ThrowStatement ( throw )
ContinueStatement ( continue )
BreakStatement ( break )
ReturnStatement ( return )
复合语句(由简单语句复合而来)

BlockStatement ( {...somecode} )
IfStatement ( if(){...somecode} )
IterationStatement
VariableStatement
对象

Object 属性值有 Data 和 Accessor，其中数据属性值用于描述状态，访问器属性用于描述行为。数据属性值中如果存储函数，也可以用于描述行为。
除了常见的 Object 是对象之外，Array、Function 都是特殊的对象。其中 Array 就是带有[[length]]s 属性的对象；Function 就是带有[[Call]]内置属性的对象
JS 标准里面有哪些对象是我们无法实现的，都有哪些特性
Bound Function Exotic Objects
properties
[[BoundTargetFunction]]: The wrapped function object.
[[BoundThis]]: The value that is always passed as the this value when calling the wrapped function.
[[BoundArguments]]: A list of values whose elements are used as the first arguments to any call to the wrapped function.
methods:
[[Call]] ( thisArgument, argumentsList )
[[Construct]] ( argumentsList, newTarget )
BoundFunctionCreate ( targetFunction, boundThis, boundArgs )
Array Exotic Objects
methods
[[DefineOwnProperty]] ( P, Desc )
ArrayCreate ( length [ , proto ] )
ArraySpeciesCreate ( originalArray, length )
ArraySetLength ( A, Desc )
String Exotic Objects
methods
[[GetOwnProperty]] ( P )
[[DefineOwnProperty]] ( P, Desc )
[[OwnPropertyKeys]] ( )
StringCreate ( value, prototype )
StringGetOwnProperty ( S, P )
Arguments Exotic Objects
methods
[[GetOwnProperty]] ( P )
[[DefineOwnProperty]] ( P, Desc )
[[Get]] ( P, Receiver )
[[Set]] ( P, V, Receiver )
[[Delete]] ( P )
CreateUnmappedArgumentsObject ( argumentsList )
CreateMappedArgumentsObject ( func, formals, argumentsList, env )
MakeArgGetter ( name, env )
MakeArgSetter ( name, env )
Integer-Indexed Exotic Objects
methods
[[GetOwnProperty]] ( P )
[[HasProperty]] ( P )
[[DefineOwnProperty]] ( P, Desc )
[[Get]] ( P, Receiver )
[[Set]] ( P, V, Receiver )
[[OwnPropertyKeys]] ( )
IntegerIndexedObjectCreate ( prototype, internalSlotsList )
IntegerIndexedElementGet ( O, index )
IntegerIndexedElementSet ( O, index, value )
Module Namespace Exotic Objects
properties
[[Module]]: The Module Record whose exports this namespace exposes
[[Exports]]: A List containing the String values of the exported names exposed as own properties of this object.
[[Prototype]]: This slot always contains the value null.
methods
[[SetPrototypeOf]] ( V )
[[IsExtensible]] ( )
[[PreventExtensions]] ( )
[[GetOwnProperty]] ( P )
[[DefineOwnProperty]] ( P, Desc )
[[HasProperty]] ( P )
[[Get]] ( P, Receiver )
[[Set]] ( P, V, Receiver )
[[Delete]] ( P )
[[OwnPropertyKeys]] ( )
ModuleNamespaceCreate ( module, exports )
Immutable Prototype Exotic Objects
methods
[[SetPrototypeOf]] ( V )
SetImmutablePrototype ( O, V )