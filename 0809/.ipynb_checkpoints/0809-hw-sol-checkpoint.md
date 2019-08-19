## 1. Loop문 연습
- 20 의 약수들을 모은 어떤 리스트를 만들어봅시다.
	```python
	factors_of_20 = []
    for i in range(1, 21, 1):
        if 20 % i == 0:
            factors_of_20.append(i)
	```
    
## 2. Loop문 연습2
- 구구단 출력하기.
```
1 * 1 = 1
1 * 2 = 2
....
9 * 9 = 81
```
이 출력 되도록 해 보세요.
```python
for i in range(1, 10, 1):
    for j in range(1, 10, 1):
        print('{} * {} = {}'.format(i, j, i * j))
```

## 3. List 연습 1
- list 내 최대값 구하기. 
- `lst = [2, 3, 6, 2, -1, 0, 6, 2, 3]` 이 주어져 있을 때 최대값인 6을 출력해보세요.
- 힌트1) 간단하게 `max(lst)` 로도 구할 수 있지만, `max()`를 쓰지 않고 loop로 해결해 보세요.

```python
# Target list
lst = [2, 3, 6, 2, -1, 0, 6, 2, 3]

# Initialize max_val
max_val = -999

# Get the maximum value in lst
for v in lst:
    # if max_val is no longer the maximum value
    #  because of v that is larger than max_val
    if max_val < v: 
        # v should be the new maximum value
        max_val = v

print(max_val)
```
출력 결과
```
6
```

## 4. List 연습 2
- list 내 최대값을 갖는 원소가 몇 개인지 구해보세요.
- `lst = [2, 3, 6, 2, -1, 0, 6, 2, 3]` 이 주어져 있을 때, 최대값인 6은 2개 있습니다. 여기서 6의 개수인 2를 출력해 보세요.
- 이 때 다음과 같은 포맷으로 출력해 보세요: 'max = 6, num_max = 2'.

```python
# Target list
lst = [2, 3, 6, 2, -1, 0, 6, 2, 3]

# Get the maximum values
max_val = max(lst)

# Count how many max_val are there in lst
num_max_val = 0
for v in lst:
    if v == max_val:
        num_max_val = num_max_val + 1
        
print('max = {}, num_max = {}'.format(max_val, num_max_val))
```
출력 결과
```
max = 6, num_max = 2
```

## 5. Dictionary 연습 
- word_freqs 함수를 구현해 보세요.
    - **input**: 어떤 string. string 내 각 단어는 space로 구분되어 있음.
    - **output**: 어떤 dictionary. 이 때 key는 input내 각 단어를 말하고 value는 key 의 등장 횟수(frequency) 를 말함.
- sol
    ```python
    def word_freqs(sentence):
        words = sentence.split(' ')
        freqs = {}

        for word in words:
            if word not in freqs:
                freqs[word] = 0
            freqs[word] += 1

        return freqs

    s = "I am a boy you are a girl"
    freq_dict = word_freqs(s)
    print(freq_dict)
    ```
    출력 결과
    ```
    {'girl': 1, 'a': 2, 'you': 1, 'are': 1, 'I': 1, 'boy': 1, 'am': 1}
    ```

## 6. 함수 연습
- 어떤 단어의 시작 알파벳 구하기.
- **함수 이름**: get_1st_alpha
- **input**: 어떤 string 한 개
- **output**: input의 가장 앞 알파벳
- 예) 
    ```python
    def get_1st_alpha(s):
        return s[0]
    
    word = "apple"
    alpha = get_1st_alpha(word)
    print(alpha)
    ```
    출력 결과
    ```
    a
    ```
    
## 7. Dictionary 연습 
- 단어들을 시작 알파벳별로 분류하는 함수를 만들어 보자.
- **함수 이름**: classify_words
- **input**: 단어(string)들의 list
- **output**: 어떤 dictionary
    - key: 어떤 알파벳
    - val: input 내의 단어들 중 key로 시작하는 것들을 모은 list
- sol
    ```python
    def classify_words(word_lst):
        classifier = {}
        for word in word_lst:
            fst_alphabet = word[0]
            if fst_alphabet not in classifier:
                classifier[fst_alphabet] = []
            classifier[fst_alphabet].append(word)
        return classifier

    word_lst = ["apple", "bear", "person", "aurora", "print", "boy"]
    classifier = classify_words(word_lst)
    print(classifier)
    ```
    출력 결과 (dictionary 내의 key나 value의 순서는 달라도 됨.)
    ```
    {'p': ['print', 'person'], 'a': ['apple', 'aurora'], 'b': ['bear', 'boy']}
    ```
    