# shell-script
shell we dance?  
 
## 순서  

[read from command line](#read-from-command-line)


## 1. read from command line  
```
read -p "Enter [Y/N] : " answer  
```

# 2. Arithmetic operation  

이것을 사용 : **$((EXPR))**

```
result=100+200
echo $result

// output : 100+200
```

```
result=$((100+200))
echo $result

// output : 300
```

# 3. Iteration  

## 3.1. for loop with seq  
* **seq** : 순서대로 숫자를 출력.  

```sh
SET=$(seq 1 10)

for i in $SET
do
  echo $i
done
```
* 예제 : 시작 포트 주소와 갯수를 받아서 서버를 실행시킨다.  

```sh
#! /bin/bash

read -p "Start port number : " port 
read -p "the number of server : " cnt

SET=$(seq $port $(($port+$cnt)))

for i in $SET
do
    echo "run server with port : $i"
    node serv.js $i &
done
```


