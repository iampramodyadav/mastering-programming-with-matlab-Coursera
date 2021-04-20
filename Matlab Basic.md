# Matlab basic
- **MATLAB Expo**
- **Abort** in order to abort a command in MATLAB, *hold down the control key and press c* to generate a local abort with MATLAB.

- **The Semicolon (;)** If a semicolon (;) is typed at the end of a command, the output of the command is not displayed

- **Typing %** When per cent symbol (%) is typed in the beginning of a line, the line is designated as a [[Comments]]. When the enter key is pressed, the line is not executed.

- **The clc Command** Typing clc command and pressing enter cleans the command window. Once the clc command is executed, a clear window is displayed.

- **Help**MATLAB has a host of built-in functions. For a complete list, refer to MATLAB user’s guide or refer to the on-line Help. To obtain help on a particular topic in the list, e.g., inverse, type help inv.

- **Statements and Variables**Statements have the form

```matlab
>> variable = expression
```
The equals (“=”) sign implies the assignment of the expression to the variable. For instance, to enter a 2 × 2
matrix with a variable name A, we write
```matlab
>> A == [1 2 ; 3 4] 〈ret〉
```
The statement is executed after the carriage return (or enter) key is pressed to display
```matlab
A =
		1		 2
		3		 4
```
## [[Math Operators]]
| Arithmetic operation | Symbol | Example |
| -------------------- | ------ | ------- |
| Addition             | +      | 6+3=9   |
| Subtraction          | -      | 6-3=3   |
| Multiplication       | *      | 2 * 2=4 |
| Right division       | /      | 6/3=2   |
| Left division        | \      | 6\3=0.5 |
| Exponentiation       | ^      | 6^3=216 |
|                      |        |         |
## DISPLAY FORMATS
| Command        | Description                                                                         | Example                          |
| -------------- | ----------------------------------------------------------------------------------- | -------------------------------- |
| format short   | Fixed-point with 4 decimal digits                                                   | >> 351/7 ans = 50.1429           |
| format long    | Fixed-point with 14 decimal digits                                                  | >> 351/7 ans = 50.14285714285715 |
| format short e | Scientific notation with 4 decimal digits                                           | >> 351/7 ans = 5.0143e + 001     |
| format long e  | Scientific notation with 15 decimal digits                                          | >> 351/7 ans = 5.0143e + 001     |
| format short g | format short g Best of 5 digit fixed or floating point                              | >> 351/7 ans = 50.143            |
| format long g  | Best of 15 digit fixed or floating point                                            | >> 351/7 ans = 50.1428571428571  | 
| format bank    | Two decimal digits                                                                  | >> 351/7 ans = 50.14             |
| format compact | Eliminates empty lines to allow more lines with information displayed on the screen |                                  |
| format loose   | Adds empty lines (opposite of compact)                                              |                                  |
## ELEMENTARY MATH BUILT-IN FUNCTIONS

- **abs(x)** Computes the absolute value of x.
- **sqrt(x)** Computes the square root of x.
- **round(x)** Rounds x to the nearest integer.
- **fix(x)** Rounds (or truncates) x to the nearest integer toward 0.
- **floor(x)** Rounds x to the nearest integer toward –∞
- **ceil(x)** Rounds x to the nearest integer toward ∞.
- **sign(x)** Returns a value of –1 if x is less than 0, a value of 0 if x equals 0, and a value of 1 otherwise.
- **rem(x,y)** Returns the remainder of x/y. for example, rem(25, 4) is 1, and
rem(100, 21) is 16. This function is also called a modulus function.
- **exp(x)** Computes ex, where e is the base for natural logarithms, or
approximately 2.718282
- **log(x)** Computes ln x, the natural logarithm of x to the base e.
- **log10(x)** Computes log10 x, the common logarithm of x to the base 10.

### Exponential functions
| Exponential functions | Description      |
| --------------------- | ---------------- |
| exp(x)                | Exponential ($e^x$) |
| log(x)                | Exponential ($e^x$) |
| log10(x)              | Exponential ($e^x$) |
| sqrt(x)               | Square root      |

### Complex number functions
- **conj(x)** Computes the complex $conjugate$ of the complex number $x$. Thus, if $x$ is equal to $a + ib$, then $conj(x)$ will be equal to a – ib.
- **angle(x)** Computes the real portion of the complex number x.
- **real(x)** Computes the imaginary portion of the complex number $x$.
- **imag(x)** Computes the absolute value of magnitude of the complex number x.
- **abs(x)** Computes the angle using the value of $atan2(imag(x), real(x))$; thus, the angle value is between $–π$ and $π$.

## [[VARIABLE NAMES]]
- A variable is a name made of a letter or a combination of several letters and digits.
- ariable names can be up to 63 (in MATLAB 7) characters long (31 characters on MATLAB 6.0).
- MATLAB is case sensitive. For instance, XX, Xx, xX and xx are the names of four different variables.
- It should be noted here that not to use the names of a built-in functions for a variable. For instance, avoid using: sin, cos, exp, sqrt, ..., etc. Once a function name is used to define a variable, the function cannot be used

### PREDEFINED VARIABLES
| Predefined variable in MATLAB | Description                                                                                               |
| ----------------------------- | --------------------------------------------------------------------------------------------------------- |
| ans                           | Represents a value computed by an expression but not stored in variable name.                             |
| pi                            | number π                                                                                                  |
| eps                           | floating-point precision for the computerbeing used. This is the smallest difference between two numbers. |
| inf                           | Represents infinity                                                                                       |
| i                             | Defined as $sqrt(−1)$ , which is: $0 + 1.0000i$.                                                          |
| j                             | Same as i.                                                                                                |
| NaN                           | Stands for Not a Number                                                                                   |
| clock                         | current time in a six-element row vector                                                                  |
| date                          | current date in a character string format                                                                 |
### COMMANDS FOR MANAGING VARIABLES
- **clear** Removes all variables from the memory. 
- **clear x, y, z** Clears/removes only variables x, y and z from the memory.
- **who** Lists the variables currently in the workspace.
- **whos** Displays a list of the variables currently in the memory and their size together with information about their bytes and class.

## GENERAL COMMANDS
### On-line help

- **help** -Lists topics on which help is available.
- **helpwin** -Opens the interactive help window.
- **helpdesk** -Opens the web browser based help facility
- **help** *topic* -Provides help on topic
- **lookfor** *string* -Lists help topics containing string
- **demo** -Runs the demo program.
### Workspace information
- **who** Lists variables currently in the workspace
- **whos** Lists variables currently in the workspace with their size
- **what** Lists m-, mat- and mex-files on the disk.
- **clear** Clears the workspace, all variables are removed.
- **clear** *x y z* Clears only variables x, y, and z.
- **clear all**Clears all variables and functions from workspace
- **mlock** *fun* Locks function fun so that clear cannot remove it.
- **munlock** *fun* Unlocks function fun so that clear can remove it.
- **clc** Clears command window, command history is lost
- **home** Same as clc.
- **clf** Clears figure window
### Directory information

- **pwd** Shows the current working directory.
- **cd**Changes the current working directory.
- **dir** Lists contents of the current directory.
- **ls** Lists contents of the current directory, same as dir.
- **path** Gets or sets MATLAB search path.
- **editpath** Modifies MATLAB search path.
- **Copies** a file.
- **mkdir** Creates a directory.

### General information
- **computer** Tells you the computer type you are using.
- **clock** Gives you wall clock time and date as a vector.
- **date** Tells you the date as a string.
more Controls the paged output according to the screen size.
- **ver** Gives the license and the version information about MATLAB installed on your computer.
- **bench** Benchmarks your computer on running MATLAB compared to other computers.
- **c (Control-c)** Local abort, kills the current command execution.
- **quit** Quits MATLAB.
- **exit** Same as quit.

## factorial, sqrt, nthroot


```matlab
>> factorial(9)

ans =

      362880

>> sqrt(7)

ans =

    2.6458

>> 7^0.5

ans =

    2.6458

>> home
>> 9^(1/2)

ans =

     3

>> sqrt(89)

ans =

    9.4340

>> help nthroot
 nthroot Real n-th root of real numbers.
 
    nthroot(X, N) returns the real Nth root of the elements of X.
    Both X and N must be real, and if X is negative, N must be an odd integer.
 
    Class support for inputs X, N:
       float: double, single
 
    See also power.

    Reference page for nthroot
    Other functions named nthroot

 .^  Array power.
    Z = X.^Y denotes element-by-element powers. X and Y must have
    compatible sizes. In the simplest cases, they can be the same size or
    one can be a scalar. Two inputs have compatible sizes if, for every
    dimension, the dimension sizes of the inputs are either the same or one
    of them is 1.
 
    C = power(A,B) is called for the syntax 'A .^ B' when A or B is an
    object.
 
    See also mpower, nthroot, realpow.

    Reference page for power
    Other functions named power

>> home
>> nthroot(27,3)

ans =

     3

>> nthroot(51,7)

ans =

    1.7536

>> 27^(1/3)

ans =

     3

>> x=9;
>> b=sqrt(45)+45

b =

   51.7082

>> 
>> b=sqrt(x)+45

b =

    48

>> home
>> sym(sqrt(89333))
 
ans =
 
89333^(1/2)
 
>> pretty(ans)
sqrt(89333)

>> pretty ans
Undefined function 'pretty' for input arguments of type 'char'.
 
>> pretty(ans)
sqrt(89333)

>> sym(1/2+2/3)
 
ans =
 
7/6
 
>> pretty(ans)
7
-
6

>> double(ans)

ans =

    1.1667

>> home
>> factorial(4)-12*(factorial(7)/factorial(9))

ans =

   23.8333

>> sqrt(34)-12*sqrt(98)+67-(1/sqrt(5))

ans =

  -46.4102

>> x=225

x =

   225

>> sqrt(sin(x))

ans =

   0.0000 + 0.9644i
```

## Trigonometry in matlab
1. **sin(x)** Computes the sine of x, where *x is in radians*.
2. **cos(x)** Computes the cosine of x, where *x is in radians*.
3. **tan(x)** Computes the tangent of x, where *x is in radians.*
4. **asin(x)** Computes the *arcsine or inverse sine*of *x, where x must be between –1 and 1* The function returns an angle in radians between –π/2 and π/2
5. **acos(x)** Computes the *arccosine or inverse cosine* of x, where x must be between –1 and 1. The function returns an angle in radians between 0 and π.
6. **atan(x)** Computes the arctangent or inverse tangent of x. The function returns an angle in radians between –π/2 and π/2.
7. **atan2(y,x)** Computes the arctangent or inverse tangent of the value y/x. The function returns an angle in radians that will be between –π and π, depending on the signs of x and y.
8. **sinh(x)** Computes the hyperbolic sine of x, which is equal to $$\frac{e^x-e^{-x}}{2}$$
9. **cosh(x)** Computes the hyperbolic cosine of x, which is equal to $$\frac{e^x+e^{-x}}{2}$$
10. **tanh(x)** Computes the hyperbolic tangent of x, which is equal to $$\frac{sinhx}{coshx}$$ 
11. **asinh(x)** Computes the inverse hyperbolic sine of x, which is equal to $$ln (x+\sqrt{x^2+1})$$
12. **acosh(x)** Computes the inverse hyperbolic cosine of x, which is equal to $$ln (x+\sqrt{x^2-1})$$
13. **atanh(x)** Computes the inverse hyperbolic tangent of x, which is equal to $$ln\sqrt{\frac{1+x}{1-x}}$$ for $|x|\leq1$
14. ** sind(degree)** =>here angle is in *degree* (add *d* in last of trigonometrical function)

```matlab
>> sin(30)

ans =

   -0.9880

>> sin(pi)

ans =

   1.2246e-16

>> cos(45)

ans =

    0.5253

>> tan(45)

ans =

    1.6198

>> %angles in radian
>> cot(48)

ans =

    0.8332

>> %convet radian to degrees
>> degrees=radians*180/pi;
Undefined function or variable 'radians'.
 
>> radians=degrees*pi/180;
Undefined function or variable 'degrees'.
 
>> sin(45)

ans =

    0.8509

>> sin(45*pi/180)

ans =

    0.7071

>> pretty
Undefined function or variable 'pretty'.
 
>> pretty(ans)
Undefined function 'pretty' for input arguments of type 'double'.
 
>> aqrt(2)/2
Undefined function or variable 'aqrt'.
 
Did you mean:
>> sqrt(2)/2

ans =

    0.7071

>> home
>> sin(43)

ans =

   -0.8318

>> sin^-1(45)
 sin^-1(45)
       ↑
Error: Invalid expression. When calling a function or indexing a variable, use
parentheses. Otherwise, check for mismatched delimiters.
 
Did you mean:
>> assin(0.1)
Undefined function or variable 'assin'.
 
Did you mean:
>> asin(0.1)

ans =

    0.1002
```
### inverse functions
```matlab
>> acos(12)

ans =

   0.0000 + 3.1763i

>> acos(0.2)

ans =

    1.3694

>> home
>> acos(0.6)

ans =

    0.9273

>> ans*180/pi

ans =

   53.1301

>> asin(0.707)

ans =

    0.7852

>> ans*180/pi

ans =

   44.9913

>> sin(45*pi/180)

ans =

    0.7071

>> asin(ans)

ans =

    0.7854

>> ans*180/pi

ans =

   45.0000

>> 
```

If you want to find cos(45) and 45 is in degree
```matlab
>> cosd(45)

ans =

    0.7071

>> sind(30)

ans =

    0.5000

>> tand(45)

ans =

     1

>> cotd(30)

ans =

    1.7321

>> 
```
## Hyperbolic Trigonometrical Function {.S1}

```matlab
cosh(0.55)
```

ans = 1.1551

```matlab
tanh(3)
```

ans = 0.9951

```matlab
cosh(54)
```

ans = 1.4154e+23

```matlab
sin(123)
```

ans = -0.4599

## Inverse Hyperbolic {.S7}

similar to sine cosine

```matlab
asinh(39)
```

ans = 4.3569

```matlab
atanh(56)
```

ans = 0.0179 + 1.5708i

## Exponential, , and Ln Function {.S1}

```matlab
e
```

Undefined function or variable 'e'.

e is not recognisable as exponential

```matlab
exp(10)
```

ans = 2.2026e+04

```matlab
exp(2)
```

ans = 7.3891

```matlab
2.7183\^2
```

ans = 7.3892

## Logarithmic {.S1}

```matlab
log(3)
```

ans = 1.0986

this natural log base e, here ln(x)=log(x)

```matlab
log(5)
```

ans = 1.6094

```matlab
log(10)
```

ans = 2.3026

for base 10=log10(x)

```matlab
log10(1000)
```

ans = 3

```matlab
log10(10)
```

ans = 1

```matlab
log10(11.5)
```

ans = 1.0607

```matlab
log(exp(1))
```

ans = 1

## Introduction to complex numbers {.S1}

```
i
```

ans = 0.0000 + 1.0000i

```
j
```

ans = 0.0000 + 1.0000i

i and j are same

```
2-i
```

ans = 2.0000 - 1.0000i

```
(2-1i)\*i
```

ans = 1.0000 + 2.0000i

```
(1-4i)-(5-4i)
```

ans = -4

```
(1-4i)\*(1+4i)
```

ans = 17

```matlab
i\*i
```

ans = -1

```matlab
sqrt(-1)
```

ans = 0.0000 + 1.0000i

```matlab
a=3-i;

b=7+5i;

a\*b
```

ans = 26.0000 + 8.0000i

```
a-b
```

ans = -4.0000 - 6.0000i

```
a^b
```

ans = -1.4773e+04 - 5.6048e+03i

## abs() {.S7}

```
c=2;

d=-5;

p=5i;

abs(d)
```

ans = 5

```
abs(p)
```

ans = 5

```
abs(b)
```

ans = 8.6023

```
abs(a)
```

ans = 3.1623

## angle() {.S7}

angle between complex and real part in radian

```
angle(a)
```

ans = -0.3218

```
angle(c)
```

ans = 0

```
angle(d)*180/pi
```

ans = 180

## real() {.S7}

```
real(a)
```

ans = 3

## imag() {.S7}

```
imag(a)
```

ans = -1

```
imag(d)
```

ans = 0

## conj( ) or ( )' {.S7}

```
conj(a)
```

ans = 3.0000 + 1.0000i

```
a'
```

ans = 3.0000 + 1.0000i

## complex(x,y) {.S7}

```
complex(5,6)
```

ans = 5.0000 + 6.0000i

# symbolic toolbox and complex number {.S13}

```
a
```

a = 3.0000 - 1.0000i

```
log(a)
```

ans = 1.1513 - 0.3218i

```
b
```

b = 7.0000 + 5.0000i

```
exp(a)
```

ans = 10.8523 - 16.9014i

```
sin(a)
```

ans = 0.2178 + 1.1634i

```
sym(angle(a))
```

ans = 2

```
a=3+3i
```

a = 3.0000 + 3.0000i

```
sym(angle(a))
```

ans = π/4

```
a=1+i
```

a = 1.0000 + 1.0000i

```
abs(a)
```

ans = 1.4142

```
sym(abs(a))
```

ans=2

```
(4-5i)*(5+6i)
```

ans = 50.0000 - 1.0000i