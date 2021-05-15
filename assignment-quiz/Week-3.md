# week-3
- [[#Assignment: Mixed Mode Arithmetic|Assignment: Mixed Mode Arithmetic]]
	- [[#Problem 1: Edge Detection|Problem 1: Edge Detection]]
	- [[#Problem 2: Audio Mixer|Problem 2: Audio Mixer]]
- [[#Assignment: Linear Equations|Assignment: Linear Equations]]
	- [[#Problem: Electric circuit|Problem: Electric circuit]]
	- [[#Problem: Linear Regression|Problem: Linear Regression]]
- [[#Practice Quiz • Live Scripts|Practice Quiz • Live Scripts]]

## Assignment: Mixed Mode Arithmetic
### Problem 1: Edge Detection
Write a function that detects the edge of objects in an image.
```matlab
function out = edgy(in)
    [n, m] = size(in);
    out = zeros(n-2,m-2);
    [n, m] = size(out);
    %for calc
    in = double(in);
    
    m1 = [-1 0 1; -2 0 2; -1 0 1];
    m2 = [1 2 1; 0 0 0; -1 -2 -1];
    
    
    for ii = 1:n
        
        for jj = 1:m
            sx = in(ii:ii+2,jj:jj+2) .* m1;
            sy = in(ii:ii+2,jj:jj+2) .* m2;
            %output pixel value
            out(ii,jj) = sqrt(sum(sum(sx(:)))^2 + sum(sum(sy(:)))^2);
        end
        
    end
    
  %convrt again
    out = uint8(out);
end 
```

**SOLUTION-2**
```MATLAB
function out = edgy(in)
    % Get the size of the input image
    [r, c] = size(in);
    
    % Create an output array that is two rows and columns smaller
    out = zeros(r-2,c-2);
    
    % Use the size of the new array for looping
    [r, c] = size(out);
    
    % Convert to double for doing calculations
    in = double(in);
    
    % Create the horizontal and vertical edge detector filters
    ex = [-1 0 1; -2 0 2; -1 0 1];
    ey = [1 2 1; 0 0 0; -1 -2 -1];
    for ii = 1:r
        for jj = 1:c
            sx = in(ii:ii+2,jj:jj+2) .* ex;
            sy = in(ii:ii+2,jj:jj+2) .* ey;
            % Calculate the output pixel value
            out(ii,jj) = sqrt(sum(sum(sx(:)))^2 + sum(sum(sy(:)))^2);
        end
    end
    % Convert back to uint8
    out = uint8(out);
end
```

### Problem 2: Audio Mixer
Write a function that mix a multi-column audio recording into one single record.
```matlab
function v = mixit(M,N)
	if size(M,2) ~= length(N)
		v = [];
	else
		N = N(:);
		M = (2*double(M)/(2^16-1))-1;
		v = M*N;
		if max(abs(v)) > 1; %if max of the abs value greater than 1
		    v = v/max(abs(v));  %devide entire vector wth that
		end
	end
end
```

## Assignment: Linear Equations
### Problem: Electric circuit
Write a function called voltage that computes the voltages at different junctions. (A,B,C)
```matlab
function sol = voltage(V,R)
        M = [R(2)*R(7) + R(1)*R(2) + R(1)*R(7),                -R(1)*R(2),                               0;
            -R(3)*R(4)*R(8),   R(4)*R(7)*R(8) + R(3)*R(4)*R(8) + R(3)*R(4)*R(7) + R(3)*R(7)*R(8),  -R(3)*R(4)*R(7);
            0,                                  -R(5)*R(6),                        R(6)*R(8) + R(5)*R(6) + R(5)*R(8)];
    
        y = V*[R(2)*R(7);R(4)*R(7)*R(8);R(6)*R(8)];
        
    	sol = M\y;
    
end
```
### Problem: Linear Regression
Given a set of approximate x and y coordinates of points in a plane, determine the best fitting line in the least square sense. Using the standard formula of a line: ax + b = y,compute a and b. That is, write a function called lin\_reg that takes two row vectors of the same length called x and y as input arguments(containing x and y coordinates of points)and returns two scalars, a and b specifying the line, as output arguments. Here is an example run:
```matlab
function [a, b] = lin_reg(x,y)

    M = [x; ones(1,length(x))]';
    s = M \ y';
    
    a = s(1);
    b = s(2);
end
```
## Practice Quiz • Live Scripts
1.Question How is a Live Script different from a regular script?
*A Live Script combines regular text and MATLAB code. It allows the user to create a nicely formatted document with embedded code and the output of the code such as plots*.
2.Question What are the parts that make up a Live Script called?
*Sections*
3.Question What is the file extension of Live Scripts?
*mlx*