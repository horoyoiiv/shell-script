

# function in shell script  
[참고](http://blog.redjini.com/281)  

### 1. function keyword를 사용  
* function keyword는 생략가능하다.  
* 함수의 선언은 호출보다 **위에 있어야** 한다.  

```sh
#! /bin/zsh

function foo(){
  echo "hello world"
}

boo(){
  echo "without function keyword"
}

foo
boo
```

### 2. 지역변수  
* **local 키워드**를 통해 함수 내에서 지역변수 선언.  
```
#! /bin/zsh

value=123123

function(){
   local value=321321
   echo "$value"
}
```

### 3. 매개변수  
* 함수 호출 후 한칸 씩 띄워서 자연스럽게 넘긴다.  
* 함수 내에서 $1, $2 등을 통해 자연스럽게 받는다.  

```
#! /bin/zsh

function boo(){
    echo "$1 $2"
}

boo 8723 1234
```


