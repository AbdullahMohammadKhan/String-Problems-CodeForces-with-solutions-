http://codeforces.com/problemset/problem/1220/A



A. Cards
time limit per test2 seconds
memory limit per test256 megabytes
inputstandard input
outputstandard output
When Serezha was three years old, he was given a set of cards with letters for his birthday. They were arranged into words in the way which formed the boy's mother favorite number in binary notation. Serezha started playing with them immediately and shuffled them because he wasn't yet able to read. His father decided to rearrange them. Help him restore the original number, on condition that it was the maximum possible one.

Input
The first line contains a single integer n (1⩽n⩽105) — the length of the string. The second line contains a string consisting of English lowercase letters: 'z', 'e', 'r', 'o' and 'n'.

It is guaranteed that it is possible to rearrange the letters in such a way that they form a sequence of words, each being either "zero" which corresponds to the digit 0 or "one" which corresponds to the digit 1.

Output
Print the maximum possible number in binary notation. Print binary digits separated by a space. The leading zeroes are allowed.

Examples
inputCopy
4
ezor
outputCopy
0 
inputCopy
10
nznooeeoer
outputCopy
1 1 0 
Note
In the first example, the correct initial ordering is "zero".

In the second example, the correct initial ordering is "oneonezero".


My boring solution:

```python
import sys
n=int(input())
name = sys.stdin.readline().strip()
#print(name)
#print(name.count("z"))
#print(name.count("n"))
for j in range(name.count("n")):
    print(1,end=" ")
for i in range(name.count("z")):
    print(0,end=" ")



```

```python
input()
c=input().count
print(*[1]*c('n')+[0]*c('z'))
```


```python
input(); l=input().count; print('1 '*l('n')+'0 '*l('z'))
```


```python
n=int(input())
s=input()
a=s.count("n")
b=s.count("z")
print ("1 "*a+"0 "*b)
```
```python
n=int(input())
s=input()
x=s.count('z')
y=(n-4*x)//3
print('1 '*y+'0 '*x)
```
```python
n = int(input())
s = input()
a = s.count("z")
b = (n - a * 4) // 3
print("1 " * b + "0 " * a)
```

```python
n=int(input())
s=input()
a=s.count("n")
b=s.count("z")
c=["1"]*a
d=["0"]*b
print(" ".join(c+d))
```
```python
input()
s=input()
print("1 "*s.count("n")+"0 "*s.count("z"))
```
```python
x=input()
y=input()
print('1 '*y.count('n'),end="")
print('0 '*y.count('z'))
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
```python

```
