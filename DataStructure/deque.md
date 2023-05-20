# Deque

- 양방향 큐 (double-ended queue)
- 하이브리드 선형 구조
  - 따라서 하나의 `deque`를 가지고 `stack`과 `queue`역할 모두 구현 가능
- 한쪽 끝(FRONT)에서 데이터의 삽입과 추출, 다른 한쪽 끝(REAR)에서 데이터의 삽입과 추출이 가능
  - `deque.append` : 오른쪽 끝에 데이터를 삽입
  - `deque.appendleft` : 왼쪽 끝에 데이터를 삽입
  - `deque.pop` : 오른쪽 끝의 데이터를 추출
  - `deque.popleft` :왼쪽 끝의 데이터를 추출

### Beackjoon Q.10866: 덱

🔗[https://www.acmicpc.net/problem/10866](https://www.acmicpc.net/problem/10866)

```python
import sys
from collections import deque

N = int(sys.stdin.readline())
deque = deque()

for _ in range(N):
    oper = sys.stdin.readline().split()

    if oper[0] == 'push_front':
        deque.append(oper[1])
    elif oper[0] == 'push_back' :
        deque.appendleft(oper[1])
    elif oper[0] == 'pop_front' :
        item = deque.pop() if deque else -1
        print(item)
    elif oper[0] == 'pop_back' :
        item = deque.popleft() if deque else -1
        print(item)
    elif oper[0] == 'size' :
        print(len(deque))
    elif oper[0] == 'empty' :
        size = 0 if deque else 1
        print(size)
    elif oper[0] == 'front' :
        item = deque[-1] if deque else -1
        print(item)
    elif oper[0] == 'back' :
        item = deque[0] if deque else -1
        print(item)
```
