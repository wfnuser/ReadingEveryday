select-case流程控制的实现机理

-   太长了，先略过



方法

方法声明

-   类型T和*T称为它们各自的方法的属主类型（`receiver type`）
-   类型T被称作为类型T和*T声明的所有方法的属主基类型（`receiver base type`）



不能为下列类型（显式地）声明方法

-   内置基本类型，比如`int`和`string`，不能在标准包中声明方法（试一下）
-   接口类型，但是接口类型可以拥有方法
-   除了满足上面条件的形如*T的指针类型之外的无名组合类型



指针类型的属主参数称为指针类型属主，非指针类型的属主参数称为值类型属主

方法名可以是空标识符`_`，但是无法被调用



每个方法对应着一个隐式声明的函数

-   编译器会自动隐式声明一个相对应的函数
-   隐式函数声明中，各自对应的方法声明的属主参数声明被插入到了普通参数声明的第一位
-   不能显式声明名称为这种形式的函数，因为这种形式的函数名不属于合法标识符，只能由编译器隐式声明



为指针类型属主隐式声明的方法

-   为一个非指针类型显式声明一个方法时，一个同名方法将自动隐式地为其对应的指针类型属主*T而声明
-   不排斥使用值类型属主 （不是很懂为什么要生成一个指针类型属主方法）



Pp. 216-222