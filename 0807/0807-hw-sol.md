### 1. 기본 연산 연습 1

- x라는 변수에 'abcdef'라는 string이 assign돼 있다고 했을 때, 'bcdefa' 라는 string을 얻어 보세요.

```python
x = 'abcdef'
y = x[1:] + x[0]
```

### 2. Boolean 연습

- XOR 연산을 만들어 봅시다.
- XOR (exclusive or) 은 두 개의 명제 가운데 한개만 참일 경우를 판단하는 논리 연산이다. ([위키](https://ko.wikipedia.org/wiki/배타적_논리합))
- XOR 연산의 진리표는 다음과 같다.
  - True xor True == False
  - True xor False == True
  - False xor True == True
  - False xor True == False
- 다음 코드에서 ??? 안의 값을 채워도 됩니다.
      ```python
      x = ??? # True 아니면 False 대입
      y = ??? # True 아니면 False 대입
      z = (x or y) and not(x and y)
      print(z)
      ```
      
### 3. 기본 연산 연습 3
```python
x = 2000
y = 1
z = 1
yymmdd = '%02d%02d%02d' % (x % 100, y, x)
```