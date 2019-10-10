# JWT_Brute

## Example

`eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoibmFuYSIsImFjdGlvbiI6InVwbG9hZCJ9.56wwCrB9tIgmUnYpLPxkO8GYj1soCjuu_skTlbH_Gg8`

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9 >> base64 decode >>  {"alg":"HS256","typ":"JWT"}

eyJ1c2VyIjoibmFuYSIsImFjdGlvbiI6InVwbG9hZCJ9 >> base64 decode >>  {"user":"nana","action":"upload"}

56wwCrB9tIgmUnYpLPxkO8GYj1soCjuu_skTlbH_Gg8 >> 需要指定key 加密得到
```

![](./jwt_brute_success.png)
![](./jwt-io.jpg)
## python usage:

`python3 jwt_brute.py 4.txt `


```
root@kali:~/jwt# python3 jwt_brute.py 

Usage: python jwt_brute.py dict.txt

root@kali:~/jwt# tail -n 10 4.txt 
zzzs
zzzt
zzzu
zzzv
zzzw
zzzx
zzzy
zzzz
admin
$admin$

root@kali:~/jwt# cat 4.txt |wc -l
456978

root@kali:~/jwt# python3 jwt_brute.py 4.txt 


      ___        _______     ____             _       
     | \ \      / /_   _|   | __ ) _ __ _   _| |_ ___ 
  _  | |\ \ /\ / /  | |     |  _ \| '__| | | | __/ _ \
 | |_| | \ V  V /   | |     | |_) | |  | |_| | ||  __/
  \___/   \_/\_/    |_|     |____/|_|   \__,_|\__\___|
                                                      

          Usage: python3 jwt.py dict.txt 
                                                           
For Example: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoibmFuYSIsImFjdGlvbiI6InVwbG9hZCJ9.56wwCrB9tIgmUnYpLPxkO8GYj1soCjuu_skTlbH_Gg8

             This key is  >>> $admin$
_________________________________________________________________________________________________________________________________________

Please Input Your Encode JWT Str= eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoibmFuYSIsImFjdGlvbiI6InVwbG9hZCJ9.56wwCrB9tIgmUnYpLPxkO8GYj1soCjuu_skTlbH_Gg8                                                                                                                         try admin                                                          
jwt.decode={'user': 'nana', 'action': 'upload'}

bingo11! found key --> $admin$ <--
root@kali:~/jwt# 

```

## 参考链接

https://www.freebuf.com/vuls/211842.html

https://jwt.io/
