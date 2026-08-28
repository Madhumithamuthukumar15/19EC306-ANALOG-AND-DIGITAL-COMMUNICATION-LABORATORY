# AIM:
To implement Shannon Fano coding schemes using MATLAB.

# SOFTWARE REQUIRED:
MATLAB

# PROGRAM:
# SHANNON FANO :
clc;
clear all;
close all;

m = input('Enter the no. of message ensembles : ');
z = [];
h = 0;
l = 0;

display('Enter the probabilities in descending order');

for i = 1:m
    fprintf('Ensemble %d\n', i);
    p(i) = input('');
end

a(1) = 0;

for j = 2:m
    a(j) = a(j-1) + p(j-1);
end

fprintf('\n Alpha Matrix');
display(a);

for i = 1:m
    n(i) = ceil(-1 * (log2(p(i))));
end

fprintf('\n Code length matrix');
display(n);

for i = 1:m
    int = a(i);

    for j = 1:n(i)
        frac = int * 2;
        c = floor(frac);
        frac = frac - c;
        z = [z c];
        int = frac;
    end

    fprintf('Codeword %d : ', i);
    disp(z);
    z = [];
end

fprintf('Avg. Code Length : ');

for i = 1:m
    x = p(i) * n(i);
    l = l + x;

    x = p(i) * log2(1 / p(i));
    h = h + x;
end

display(l);

fprintf('Entropy : ');
display(h);

fprintf('Efficiency : ');
display(100 * h / l);

fprintf('Redundancy : ');
display(100 - (100 * h / l));

# Input:
Enter the Number of message ensembles: 4
Enter the probabilities in ascending order Ensemble 1
0.2
Ensemble 2
0.3
Ensemble 4
0.4
Ensemble 5
0.4

# OUTPUT:
<img width="475" height="662" alt="image" src="https://github.com/user-attachments/assets/17e7ada3-5b00-4577-8f4b-78f57255d1d2" />
<img width="441" height="573" alt="image" src="https://github.com/user-attachments/assets/c5bea64a-50b4-4158-b21d-98c576f718dc" />




# RESULT:
Thus Shannon Fano coding are performed using MATLAB.

