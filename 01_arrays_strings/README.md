# Arrays and Strings


<br>

**todo**

- [ ] `medium` &nbsp; the maximum subarray  
sliding window problem, dynamic programming  
watch video of someone going through it 

- [ ] `easy` &nbsp; making anagrams 
1 wrong answer — find corner case 

- [ ] `medium` &nbsp; highest value palindrome


<br>



### `easy` &nbsp; [Java 2D Array](https://www.hackerrank.com/challenges/java-2d-array) 

Score: 10.00/10.00

<details> 
<summary>
    <code>Solution.java</code>
</summary>

<br>

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    private static final Scanner scanner = new Scanner(System.in);
    
    private int[][] arry;

    public Solution (int[][] input) {
        arry = input;
    }
    
    public int solver () {
        int max = -6 * 6 * 9;
        int curr = -6 * 6 * 9 - 1;
        for (int r = 0; r < 4; r++) {
            for (int c = 0; c < 4; c++) {
                curr = arry[r][c] + arry[r][c+1] + arry[r][c+2] + 
                                  arry[r+1][c+1] + 
                       arry[r+2][c] + arry[r+2][c+1] + arry[r+2][c+2];
                if (curr >= max) {
                    max = curr;
                }
            }
        }
        return max;
    }
    
    public static void main(String[] args) {
        int[][] arr = new int[6][6];

        for (int i = 0; i < 6; i++) {
            String[] arrRowItems = scanner.nextLine().split(" ");
            scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

            for (int j = 0; j < 6; j++) {
                int arrItem = Integer.parseInt(arrRowItems[j]);
                arr[i][j] = arrItem;
            }
        }

        scanner.close();
                
        Solution s = new Solution(arr);
        System.out.println(s.solver());

    }
}
```
<br>

*it's the forgetting the language and having to reference code from high school for me*

</details>

<br>

### `easy` [Arrays - DS](https://www.hackerrank.com/challenges/arrays-ds) 

Score: 10.00/10.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def reverseArray(a):
    return a[::-1]
```

<br>

### `easy` &nbsp; [Left Rotation](https://www.hackerrank.com/challenges/array-left-rotation)

Score: 20.00/20.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def rotateLeft(d, arr):
    return arr[d:] + arr[:d]

```

<br>

### `easy` &nbsp; [Divisible Sum Pairs](https://www.hackerrank.com/challenges/divisible-sum-pairs)

Score: 10.00/10.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def divisibleSumPairs(n, k, ar):
    total = 0
    for i in range(n):
        for j in range(i+1,n):
            if (ar[i]+ar[j])%k == 0: 
                total+=1
    return total
```

<br>

### `easy` &nbsp; [Minimum Distances](https://www.hackerrank.com/challenges/minimum-distances)

Score: 20.00/20.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def minimumDistances(a):
    dct = {i:[] for i in a}
    if len(dct.keys()) == len(a):
        return -1 
    
    for i in range(len(a)):
        dct[a[i]] += [i]
    
    mini = len(a)
    for i in dct:
        if len(dct[i]) > 1:
            combos = [abs(dct[i][a]-dct[i][b]) for a in range(len(dct[i])) for b in range(1,len(dct[i])) if a !=b and a < b]
            for j in combos:
                if j < mini:
                    mini = j
    return mini
```

<br>

### `easy` &nbsp; [Equalize the Array](https://www.hackerrank.com/challenges/equality-in-a-array)

Score: 20.00/20.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def equalizeArray(arr):
    dct = dict()
    max = -1
    for i in arr:
        dct[i] = dct.get(i,0)+1
        if dct[i] > max:
            max = dct[i]
    return len(arr) - max    
```

<br>

### `medium` &nbsp; [The Maximum Subarray](https://www.hackerrank.com/challenges/maxsubarray)

Score: /50.00 

DP - Sliding Window

```

```

<br>

### `easy` &nbsp; [CamelCase](https://www.hackerrank.com/challenges/camelcase)

Score: 15.00/15.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def camelcase(s):
    return len([i for i in s if ord(i) < 91 and ord(i) > 64]) + 1

```

<br>

### `easy` &nbsp; [Caesar Cipher](https://www.hackerrank.com/challenges/caesar-cipher-1)

Score: 15.00/15.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def move (letter,k):
    a = ord(letter)
    if (a < 91 and a > 64):
        return chr((a - 65 + k) % 26 + 65)
    elif (a < 123 and a > 96):
        return chr((a - 97 + k) % 26 + 97)
    else:
        return letter

def caesarCipher(s, k):
    shifted = ""
    for i in s:
        shifted += move(i,k)
    return shifted
```

<br>

### `easy` &nbsp; [Alternating Characters](https://www.hackerrank.com/challenges/alternating-characters)

Score: 20.00/20.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def alternatingCharacters(s):
    if len(s) == 1:
        return 0
    return len(s) - len([i for i in s.split("A") if i !=""]) - len([i for i in s.split("B") if i !=""])
```

<br>

### `easy` &nbsp; [HackerRank in a String!](https://www.hackerrank.com/challenges/hackerrank-in-a-string)

Score: 20.00/20.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def hackerrankInString(s):
    hrs = "hackerrank"
    hrl = len(hrs)
    
    if s == hrs:
        return "YES"
    
    if len(s) < hrl:
        return "NO"
    
    hr = set(hrs)
    valid = [i for i in s if i in hr]
    
    upto = -1
    
    for i in valid:
        if i == hrs[upto+1]:
            upto += 1
        if upto == hrl - 1:
            return "YES"
    
    return "NO"
```

<br>

### `easy` &nbsp; [Making Anagrams](https://www.hackerrank.com/challenges/making-anagrams)

Score: 27.86/30.00 

**1 Wrong Answer**

```python
#!/bin/python3

import math
import os
import random
import re
import sys
from functools import reduce

def makingAnagrams(s1, s2):
    if s1 == s2:
        return 0
    
    # both = {i for i in s1 if i in s2}
    # realized the set operation was faster
    both = set(s1) & set(s2)
    
    if len(both) == 0:
        return len(s1) + len(s2)
    
    l1 = [i for i in s1 if i in both]
    l2 = [i for i in s2 if i in both]
    
    first = dict()
    for i in l1: 
        first[i] = first.get(i,0)+1 

    for i in l2: 
        first[i] = first.get(i,0)-1
    
    # total length - letters common + remaining letters different 
    
    # diff = reduce((lambda x, y: abs(x) + abs(y)),first.values()) if len(first.values()) > 1 else 0
    
    return len(s1)+len(s2)-(len(l1)+len(l2))+reduce((lambda x, y: abs(x) + abs(y)),first.values())
```

<br>

### `easy` &nbsp; [The Love-Letter Mystery](https://www.hackerrank.com/challenges/the-love-letter-mystery)

Score: 20.00/20.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def mirror (a):
    b = a[::-1]
    diff = []

    for i in range(len(a)):
        if a[i] != b[i]: 
            # if the letters at the given index aren't the same, add the index to the list
            diff.append(i)
    
    return diff, int(len(diff) / 2)

def theLoveLetterMystery(s):
    if s == s[::-1]:
        return 0
    
    diff, ldiff = mirror(s)
    l = [s[i] for i in diff]
    changes = 0
    for i in range(ldiff):
        changes+=abs(ord(l[i])-ord(l[-(i+1)]))
    
    return changes
```

<br>

### `easy` &nbsp; [String Construction](https://www.hackerrank.com/challenges/string-construction)

Score: 25.00/25.00

```python
#!/bin/python3

import math
import os
import random
import re
import sys

def stringConstruction(s):
    min = set(s)
    return len(min)
```

<br>

### `medium` &nbsp; [Highest Value Palindrome](https://www.hackerrank.com/challenges/richie-rich)

Score: /30.00 

Rip

```

```

<br>

<br>

rachel stop using absurdly long and vaguely unreadable list comprehensions challenge




