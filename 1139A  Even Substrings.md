https://codeforces.com/problemset/problem/1139/A\


A. Even Substrings
time limit per test0.5 seconds
memory limit per test256 megabytes
inputstandard input
outputstandard output
You are given a string s=s1s2…sn of length n, which only contains digits 1, 2, ..., 9.

A substring s[l…r] of s is a string slsl+1sl+2…sr. A substring s[l…r] of s is called even if the number represented by it is even.

Find the number of even substrings of s. Note, that even if some substrings are equal as strings, but have different l and r, they are counted as different substrings.

Input
The first line contains an integer n (1≤n≤65000) — the length of the string s.

The second line contains a string s of length n. The string s consists only of digits 1, 2, ..., 9.

Output
Print the number of even substrings of s.

Examples
inputCopy
4
1234
outputCopy
6
inputCopy
4
2244
outputCopy
10
Note
In the first example, the [l,r] pairs corresponding to even substrings are:

s[1…2]
s[2…2]
s[1…4]
s[2…4]
s[3…4]
s[4…4]
In the second example, all 10 substrings of s are even substrings. Note, that while substrings s[1…1] and s[2…2] both define the substring "2", they are still counted as different substrings.

My solution:

```python
input()
s=input()
sum=0
for i in range(1,len(s)+1):
    if int(s[i-1])%2==0:
        sum+=int(i)
        
print(sum)
```
input(); print(sum(i + 1 if si in '2468' else 0 for i, si in enumerate(input())))
```python
n = int(input())
s = input()
print(sum(i+1 for i, l in enumerate(s) if int(l)%2 == 0))
```
```python
n = int(input())
print(sum([(pos+1) for pos, i in enumerate(input()) if int(i)%2 == 0]))
```

```python
n = int(input())
s = input()
print(sum(i + 1 for i in range(n) if int(s[i]) % 2 == 0)) 
```

```python
input()
t = input()
s = sum((1-(int(t[i])%2)) * (i+1) for i in range(len(t)))
print(s)
```

```python
n, a = int(input()), input()
print(sum(i + 1 if not int(a[i]) & 1 else 0 for i in range(n)))

```

```python
n=input()
a = input()
k=0
for i in range(len(a)):
    k+=(int(a[i])%2+1)%2*(i+1)
print(k)
```

```python
n,ans=input(),0
s=input()
for i in range(int(n)):
	if s[i] in '2468':
		ans+=i+1
print(ans)
```

```python
_, n = int(input()), input()
c = 0
for i in range(_):
	if int(n[i]) % 2 == 0: c+=i+1
print(c)
```

```python
n = int(input())
s = input()
result = 0
for i in range(n):
    if s[i] in ['0', '2', '4', '6', '8']:
        result = result + i + 1;
print(result)
```

```python
n = int(input())
s = input()
st = set(['0','2','4','6','8'])
result = 0
for i in range(n):
    result+= i+1 if s[i] in st else 0
print(result)
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

```python

```

```python

```




