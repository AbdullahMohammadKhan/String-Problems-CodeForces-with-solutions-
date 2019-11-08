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

Examples
inputCopy
4
Icosahedron
Cube
Tetrahedron
Dodecahedron
outputCopy
42
inputCopy
3
Dodecahedron
Octahedron
Octahedron
outputCopy
28
Note
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
