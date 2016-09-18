# pylot-regular-exp-match
customized pylot searching and returning a match of regular expression from page source




#### Test case:

##### html tag texts
```
<case>
<url>test_url</url>
<verify>verify_string</verify>
<regular_expressions>span:class:donationsAmount</regular_expressions>
</case>
```
  
is the equivalent of the following expression looked up in the page source content:
  ```
  <span class="donationsAmount">\d{1,6}</span>
  ```
  
##### plain regex
 
 ```
<case>
<url>test_url</url>
<verify>verify_string</verify>
<regular_expressions>plain:Latest Updates (.{1,})</regular_expressions>
</case>
 ```
is the equivalent of the following expression found in the page source:
Latest Updates (1500)



#### Report produced: 

| URL      | Response time          | Regular Expression Match  |
| ---------|:----------------------:| -------------------------:|
| test_url | 1.333434               | 10000                     |
| test_url | 1.333434               | Latest Updates (1500)     |
| test_url | 1.333434               | 13000                     |
| test_url | 1.333434               | Latest Updates (1500)     |
| test_url | 1.333434               | 13000                     |
| test_url | 1.333434               | Latest Updates (1400)     |

where the  Regular Expression Match is the text matching \d{1,6} or Latest Updates (.{1,})
 
 
#### Run: 

run.py -g -x test_regular_expr.xml -o "C:\"

Use -g for GUI for Python 2.7+ ( unless on Python 2.6)
