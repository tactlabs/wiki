/ [Home](index.md)

# Python Snippets

**Note:** All python snippets come here



Random Number filler for CSV col$
```
import random

def get_random_int(min = 1, max = 100):
   return random.randint(min, max)

def get_random_list_int(size = 10):

    int_list = []

    for _ in range(size):
        int_list.append(get_random_int())
    
    return int_list

def print_list(_list):

    for item in _list:
        print(item)

def startpy():

    int_list = get_random_list_int(100)
    print_list(int_list)
    

if __name__ == '__main__':
    startpy()
```

