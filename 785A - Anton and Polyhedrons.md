http://codeforces.com/problemset/problem/785/A


A. Anton and Polyhedrons
time limit per test2 seconds
memory limit per test256 megabytes
inputstandard input
outputstandard output
Anton's favourite geometric figures are regular polyhedrons. Note that there are five kinds of regular polyhedrons:

Tetrahedron. Tetrahedron has 4 triangular faces.
Cube. Cube has 6 square faces.
Octahedron. Octahedron has 8 triangular faces.
Dodecahedron. Dodecahedron has 12 pentagonal faces.
Icosahedron. Icosahedron has 20 triangular faces.
All five kinds of polyhedrons are shown on the picture below:


Anton has a collection of n polyhedrons. One day he decided to know, how many faces his polyhedrons have in total. Help Anton and find this number!

Input
The first line of the input contains a single integer n (1 ≤ n ≤ 200 000) — the number of polyhedrons in Anton's collection.

Each of the following n lines of the input contains a string si — the name of the i-th polyhedron in Anton's collection. The string can look like this:

"Tetrahedron" (without quotes), if the i-th polyhedron in Anton's collection is a tetrahedron.
"Cube" (without quotes), if the i-th polyhedron in Anton's collection is a cube.
"Octahedron" (without quotes), if the i-th polyhedron in Anton's collection is an octahedron.
"Dodecahedron" (without quotes), if the i-th polyhedron in Anton's collection is a dodecahedron.
"Icosahedron" (without quotes), if the i-th polyhedron in Anton's collection is an icosahedron.
Output
Output one number — the total number of faces in all the polyhedrons in Anton's collection.

## Examples

#input
4
Icosahedron
Cube
Tetrahedron
Dodecahedron
#output

42
#input
3
Dodecahedron
Octahedron
Octahedron
#output
28
#Note
In the first sample Anton has one icosahedron, one cube, one tetrahedron and one dodecahedron. Icosahedron has 20 faces, cube has 6 faces, tetrahedron has 4 faces and dodecahedron has 12 faces. In total, they have 20 + 6 + 4 + 12 = 42 faces.

```python
a=int(input())
sum=0
for i in range(a):
    c=input()
    if c=="Tetrahedron":
        sum+=4
    elif c=="Cube":
        sum+=6
    elif c=="Octahedron":
        sum+=8
    elif c=="Dodecahedron":
        sum+=12
    elif c=="Icosahedron":
        sum+=20
print(sum)

```
Here's how the masters did it:

```python
import sys
 
 
num_inputs = int(sys.stdin.readline().strip())
shape_inputs = [shape.strip() for shape in sys.stdin.readlines()]
 
POLYHEDRONS = {
    'Tetrahedron': 4,
    'Cube': 6,
    'Octahedron': 8,
    'Dodecahedron': 12,
    'Icosahedron': 20
}
 
total_sides = sum([POLYHEDRONS[shape] for shape in shape_inputs])
print(total_sides)
```
The strip() method returns a copy of the string in which all chars have been stripped from the beginning and the end of the string (default whitespace characters).
```python
from sys import stdin 
mapF = {'Icosahedron': 20, 'Cube': 6,
        'Tetrahedron': 4, 'Dodecahedron': 12, 'Octahedron':8}
 
num = int(stdin.readline())
faces = 0
 
for i in range(num):
    faces += mapF[stdin.readline().rstrip()]
 
print(faces)
```

The rstrip() method returns a copy of the string with trailing characters removed (based on the string argument passed). The rstrip() removes characters from the right based on the argument (a string specifying the set of characters to be removed).
```python
# -*- coding: utf-8 -*-
"""
Created on Wed Mar 15 08:04:38 2017
 
@author: kprashan
"""
from sys import stdin
polyDict = {"Icosahedron" : 20,
             "Cube" : 6,
             "Octahedron"  : 8,
             "Dodecahedron" : 12,
             "Tetrahedron" :4 }
array = []
for  line in stdin :
    array.append(line.rstrip())
n = int(array[0])
faces =0
for string in array[1:] :
    faces += polyDict[string]
 
print(faces)
```



```python
import sys
 
 
figures = dict(
    Tetrahedron=4,
    Cube=6,
    Octahedron=8,
    Dodecahedron=12,
    Icosahedron=20,
)
count = 0
for _ in range(int(sys.stdin.readline())):
 
    count += figures[sys.stdin.readline().strip()]
 
print(count)

```


```python
import sys
 
_ = input()
shapes = [s.strip() for s in sys.stdin.readlines()]
 
d = {
    "Tetrahedron": 4,
    "Cube": 6,
    "Octahedron": 8,
    "Dodecahedron": 12,
    "Icosahedron": 20
}
 
print(sum([d[s] for s in shapes]))
```



```python
import sys
 
data = {
    'Tetrahedron': 4,
    'Cube': 6,
    'Octahedron': 8,
    'Dodecahedron': 12,
    'Icosahedron': 20,
}
 
if __name__ == '__main__':
    lines = [x.strip() for x in sys.stdin.readlines()]
    result = 0
 
    for line in lines[1:]:
        if line in data.keys():
            result += data[line]
 
    sys.stdout.write(str(result) + '\n')


```



```python
import sys
 
shapes = [s.strip() for s in sys.stdin.readlines()][1:]
 
d = {
    "Tetrahedron": 4,
    "Cube": 6,
    "Octahedron": 8,
    "Dodecahedron": 12,
    "Icosahedron": 20
}
 
print(sum([d[s] for s in shapes]))
```



```python
import sys
from collections import defaultdict
 
shapes = defaultdict(int)
n = int(sys.stdin.readline())
 
for shape in range(n):
    name = sys.stdin.readline()[:-1]
    shapes[name] += 1
 
total = 0
total += 4*shapes["Tetrahedron"]
total += 6*shapes["Cube"]
total += 8*shapes["Octahedron"]
total += 12*shapes["Dodecahedron"]
total += 20*shapes["Icosahedron"]
 
print(total)
```


```python
import sys
 
n = int(sys.stdin.readline())
 
granes = {'Tetrahedron' : 4,
          'Cube' : 6,
          'Octahedron' : 8,
          'Dodecahedron' : 12,
          'Icosahedron' : 20}
 
ans = 0
for i in range(n):
    t = sys.stdin.readline().strip()
    ans += granes[t]
 
print(ans)
```


```python
print(sum([4,0,8,20,6,12][ord(s[0])%7]for s in(input()for i in range(int(input())))))
```


```python
i=input;print(sum({'T':4,'C':6,'O':8,'D':12,'I':20}[i()[0]]for _ in range(int(i()))))
```


```python
i=input;print(sum({'T':4,'C':6,'O':8,'D':12,'I':20}[i()[0]]for _ in range(int(i()))))
```
```python
n=int(input())
print(sum({'T':4,'C':6,'O':8,'D':12,'I':20}[input()[0]]for _ in ' '*n))
```

```python
d={'T':4,'C':6,'O':8,'D':12,'I':20};i=input;print(sum(d[i()[0]]for _ in range(int(i()))))
```
```python
n=int(input());d={'T':4,'C':6,'O':8,'D':12,'I':20}
print(sum([d[input()[0]] for i in range(n)]))
```
```python
d = {'T': 4, 'C': 6, 'O': 8, 'D': 12, 'I': 20}
print(sum(d[input()[0]] for _ in range(int(input()))))
```
```python
d={'T':4,'C':6,'O':8,'D':12,'I':20}
c=0
for i in range(int(input())):
    c+=d[input()[0]]
 
print(c)
```
```python
x = int(input())
c = {'T': 4, 'C': 6, 'O': 8, 'D': 12, 'I': 20}
print(sum([c[input()[0]] for _ in range(x)]))
```

```python
n=int(input())
d = {'T':4,'C':6,'O':8,'D':12,'I':20}
sum=0
while n:
    sum += d[input()[:1]]
    n-=1
print(sum)
```
```python

```
```python

```
```python

```
```python

```
```python

```
.
