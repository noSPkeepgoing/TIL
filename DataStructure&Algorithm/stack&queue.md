# Stack & Queue

## Stack

- LIFO(Last In First Out) 형태로 데이터 저장
- push, pop 연산
  - `push` : 데이터 삽입
  - `pop` : 데이터 추출
- 한쪽 끝(TOP)에서 삽입과 추출이 동시에 수행

### Beackjoon Q.10828: 스택

🔗[https://www.acmicpc.net/problem/10828](https://www.acmicpc.net/problem/10828)

```python
import sys

stackList = []

def stack(op):
    oper = op.split()

    if oper[0] == 'push' :
        stackList.append(int(oper[1]))
    elif oper[0] == 'pop':
        pop = stackList.pop() if len(stackList) else -1
        print(pop)
    elif oper[0] == 'size':
        print(len(stackList))
    elif oper[0] == 'empty':
        empty = 0 if len(stackList) else 1
        print(empty)
    else :
        top = stackList[-1] if len(stackList) else -1
        print(top)

N = int(sys.stdin.readline())
for i in range(N):
    stack(sys.stdin.readline())
```

## Queue

- FIFO(First In First Out) 형태로 데이터 저장
- enqueue, dequeue 연산
  - `enqueue` : 데이터 삽입
  - `dequeue` : 데이터 추출
- 한쪽 끝(REAR)에서 삽입만 수행, 그 반대 끝(FRONT)에서 추출만 수행

### Beackjoon Q.10845: 큐

🔗[https://www.acmicpc.net/problem/10845](https://www.acmicpc.net/problem/10845)

````python
import sys

queueList = []

def queue(op):
    oper = op.split()

    if oper[0] == 'push' :
        queueList.append(int(oper[1]))
    elif oper[0] == 'pop':
        pop = queueList.pop(0) if len(queueList) else -1
        print(pop)
    elif oper[0] == 'size':
        print(len(queueList))
    elif oper[0] == 'empty':
        empty = 0 if len(queueList) else 1
        print(empty)
    elif oper[0] == 'front':
        front = queueList[0] if len(queueList) else -1
        print(front)
    else :
        back = queueList[-1] if len(queueList) else -1
        print(back)


N = int(sys.stdin.readline())
for i in range(N):
    queue(sys.stdin.readline())
    ```
````
