
https://codeforces.com/problemset/problem/978/B


B. File Name
time limit per test1 second
memory limit per test256 megabytes
inputstandard input
outputstandard output
You can not just take the file and send it. When Polycarp trying to send a file in the social network "Codehorses", he encountered an unexpected problem. If the name of the file contains three or more "x" (lowercase Latin letters "x") in a row, the system considers that the file content does not correspond to the social network topic. In this case, the file is not sent and an error message is displayed.

Determine the minimum number of characters to remove from the file name so after that the name does not contain "xxx" as a substring. Print 0 if the file name does not initially contain a forbidden substring "xxx".

You can delete characters in arbitrary positions (not necessarily consecutive). If you delete a character, then the length of a string is reduced by 1. For example, if you delete the character in the position 2 from the string "exxxii", then the resulting string is "exxii".

Input
The first line contains integer n (3≤n≤100) — the length of the file name.

The second line contains a string of length n consisting of lowercase Latin letters only — the file name.

Output
Print the minimum number of characters to remove from the file name so after that the name does not contain "xxx" as a substring. If initially the file name dost not contain a forbidden substring "xxx", print 0.

Examples
inputCopy
6
xxxiii
outputCopy
1
inputCopy
5
xxoxx
outputCopy
0
inputCopy
10
xxxxxxxxxx
outputCopy
8
Note
In the first example Polycarp tried to send a file with name contains number 33, written in Roman numerals. But he can not just send the file, because it name contains three letters "x" in a row. To send the file he needs to remove any one of this letters.



My solution:
```python
l=int(input())
s=input()
n=True
#count=0
while n:
    if "xxx" in s:
        s=s.replace("xxx","xx")
        #count+=1
    else:
        n=False
        
print(l-len(s))


```
```python
input()
s=input()
print(sum(1 for i in range(len(s)-2)if s[i:i+3]=='xxx'))

```
```python
import re
input()
print(sum(len(f)-2 for f in re.findall('x{3,}',input())))
```
```python
n, s = int(input()), input()
print(sum(s[i:i+3] == 'xxx' for i in range(n - 2)))
```
```python
import re
n = int(input()); s = str(input())
print(len(re.findall("(?=xxx)", s)))
```
```python
n=int(input())
s=input()
while 'xxx' in s:
	s=s.replace('xxx','xx')
print(n-len(s))
```
```python
n, s = int(input()), input()
print(sum(1 for i, si in enumerate(s) if s[i:i + 3] == 'xxx'))
```
```python
n, s = int(input()), input()
print(sum(1 for i, si in enumerate(s) if s[i:i + 3] == 'xxx'))
```
```python

n=int(input())
s=input()
while('xxx') in s:
   s=s.replace('xxx','xx',1)
print(n-len(s))
```
```python
import re
input()
a = re.findall(r'x{3,}', input())
print(sum(map(lambda s: len(s)-2, a)))
```
```python
input()
print(sum(max(0, len(r) - 2) for r in ''.join(' x'[x == 'x'] for x in input()).split()))
```
```python
import re
 
n = int(input())
print(sum(map(lambda x: len(x) - 2, re.findall('x{3,}', input()))))
```
```python
f = lambda s: f(s.replace('xxx', 'xx')) if 'xxx' in s else s
print(int(input()) - len(f(input())))
```
```python
n=int(input())
s=input()
c=0
for i,j in enumerate(s):
  if s[i:i+3]=='xxx':
    c+=1
print(c)
```
```python
n=int(input())
s=input()
f=0
for i in range(n-2):
    if s[i:i+3]==3*'x':
        f+=1
print(f)
```

```python
import re
zxjnb = input()
s = input()
l = re.findall("x+", s)
print(sum(max(0, len(i) - 2) for i in l))
```
```python
_ = input()
l = input()
res = 0
for i in range(len(l) - 2):
    if l[i] == l[i+1] and l[i+1] == l[i+2] and l[i] == 'x':
        res += 1
print(res)
```
```python

```
```python

```
```python

```
```python

```


