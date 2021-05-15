
# Week-2
- [[#Assignment: Recursion|Assignment: Recursion]]
	- [[#Problem 1: Digit Summation|Problem 1: Digit Summation]]
	- [[#Problem 2: Maximum Element|Problem 2: Maximum Element]]
	- [[#Problem 3: Reverse a Vector|Problem 3: Reverse a Vector]]
	- [[#Problem 4: Fibonacci Series|Problem 4: Fibonacci Series]]
	- [[#Problem 5: Palindrome|Problem 5: Palindrome]]
- [[#Assignment: Variable Number of Arguments|Assignment: Variable Number of Arguments]]
	- [[#Problem 1: Name-value Pairs|Problem 1: Name-value Pairs]]
	- [[#Problem 2: Data Entry|Problem 2: Data Entry]]
- [[#Assignment: Function Handles and Nested Functions|Assignment: Function Handles and Nested Functions]]
	- [[#Problem 1: Autograder|Problem 1: Autograder]]
	- [[#Problem 2: Fun with polynomial|Problem 2: Fun with polynomial]]


## Assignment: Recursion
### Problem 1: Digit Summation

Write a recursive function to sum the individual digits of an input number.
**Solution-1**
```matlab
function s=digit_sum(n)
    if (~isscalar(n) || n~=fix(n) || n<0)
        error("n must be non negative scalar");
    end
    
    if n==0;
        s=0;
    else
        s=digit_sum(fix(n*0.1))+n-(fix(n*0.1))*10;
    end
    
end
```

**Solution-2**
```matlab
function res = cdigit_sum(n)
    if n < 10
        res = n;
    else
        res = cdigit_sum(floor(n/10)) + rem(n,10);
    end
end
```

### Problem 2: Maximum Element

Write a recursive function to find the maximum element in a vector.
**Solution-1**
```Matlab
function m=max_in(v)

n=length(v);

if n==1;
    m=v(1);
else
    m = max(v(1),max_in(v(2:n)));
end


end
```
**Solution-2**
```matlab
function m=cmax_in(v)

    n=length(v);

    if n==1;
        m=v(1);
    else
        m = cmax_in(v(2:n));
        if v(1)>m
        m = v(1);
    end


end
```

**Solution-3***
```Matlab
function mx = recursive_max(v)
    if length(v) == 1 
        mx = v(1);
    else
        % Each recursion, v(2:end) becomes smaller by 1-element
        mx = bigger(v(1),recursive_max(v(2:end)));
    end
end
% Cannot use the max function. Use helper function to return the larger of 
% two element
function c = bigger(a,b)
    c = a;
    if a < b
        c = b;
    end
end
```

### Problem 3: Reverse a Vector
Write a recursive function that returns a vector with the element of in input vector reversed
**Solution-1**
```Matlab
function w=reversal(v)
    
    if length(v)==1
        w=v;
    else
        w=[v(end),reversal(v(1:end-1))];
    end
end
```
**Solution-2**
```Matlab
function w=reversal(v)
    
    if length(v)==1
        w=v;
    else
        w=[v(end),reversal(v(1:end-1))];
    end
end
```

### Problem 4: Fibonacci Series

Write a recursive function that computes the elements of the Fibonacci series.
**Solution-1**
```matlab
function f=fibor(n)
    if ~isscalar(n) ||n~=fix(n) || n<=0
        error("non negative scaler integer input expected")
    end
    if n==1
        f=1
    elseif n==2
        f=[1 1];
    else
        p=fibor(n-1);
        f=[p sum(p(end)+p(end-1))];
    end
end
```

**solution-2**
```Matlab
function f=fibo_list(n)
    if n<=2
        f=ones(1,n);
    else
        f=fibo_list(n-1);
        f=[f f(end-1)+f(end)];
    end
end
```

### Problem 5: Palindrome

Write a recursive function that determines if the input is a palindrome.
```matlab
function p=palindrome(s)
    if length(s)==0
        p=true;
    elseif length(s)==1
        p=true;
    else
        p=(s(1)==s(end) && palindrome(s(2:(end-1))));
    end
end
```

## Assignment: Variable Number of Arguments
### Problem 1: Name-value Pairs

Write a function that pairs up the keys and the respective values from unspecified number of input
```Matlab
% Problem 1: Name-value Pairs
% Write a function that pairs up the keys and the 
% respective values from unspecified number of input

function db = name_value_pairs(varargin)

if nargin>0 && rem(nargin, 2) == 0
    db = cell(nargin/2, 2);
    
    
    for ii = 1:nargin
        if rem(ii,2) ~= 0
            if ischar(varargin{ii}) 
                db{(ii+1)/2,1} = varargin{ii};
            else
                db ={};
                return;
            end
        else
            db{ii/2,2} = varargin{ii};
        end
        
        
    end
else
    db = {};
end  
end
```

### Problem 2: Data Entry

Write a function that keys in new voters' information into the current database.
```Matlab
function database = voters(database,varargin)
    % Get the length of the input database
    count = length(database);
    
    % Create a copy of the database. This will be the new database if input
    % is valid
    tmp = database;
    
    % Names and IDs come in pairs. Increment loop counter by 2
    for ii = 1:2:length(varargin)
        % Make sure the Name is a char or string
        if ischar(varargin{ii}) || isstring(varargin{ii})
            count = count + 1;
            tmp(count).Name = string(varargin{ii});
            % Make sure there is a valid ID
            if ii+1 <= length(varargin) && isnumeric(varargin{ii+1}) && round(varargin{ii+1}) == varargin{ii+1}
                tmp(count).ID = varargin{ii+1};
            else
                % Not valid input. Return original database
                return;
            end
        else
            % Not valid input. Return orginal database
            return;
        end
    end
    % All inputs valid. Update database.
    database = tmp;
end
```

## Assignment: Function Handles and Nested Functions
### Problem 1: Autograder

Write a function that compare two different functions' results.
**Solution-1**

```Matlab
function pass = cgrader(fn1,fn2,varargin)
    pass = false;
    for ii = 1:length(varargin)
        if ~isequal(fn1(varargin{ii}),fn2(varargin{ii}))
            return;
        end
    end
    pass = true;
end
```

**Solution-2**

```Matlab
function f=grader(fn1,fn2, varargin)

    for n=1:length(varargin);
        if isequal(fn1(varargin{n}),fn2(varargin{n}));
            f=true;
        else
            f=false;
        end
    end
            
end
```

### Problem 2: Fun with polynomial

Write a function that create a function handle of polynomials. (modify to remove for loop)
```matlab
function pf = poly_fun(p)
 
    function polynomial = poly(x)
        
        polynomial=sum(p.*x.^(0:length(p)-1))
        
    end
    
    pf = @poly;
end
```