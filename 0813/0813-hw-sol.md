## 1. Palindrome
```python
def is_palindrome(word):
    alphabet_sequence = list(filter(str.isalpha, word.lower()))
    n = len(alphabet_sequence)
    
    for i, alphabet in enumerate(alphabet_sequence):

        # Check only half of the sequence
        if i == int(n / 2):
            break
        
        # Check if i-th word is matched with the last i-th word
        i_th_word = alphabet
        last_i_th_word = alphabet_sequence[n - i - 1]
        print(i_th_word, last_i_th_word)
        if i_th_word != last_i_th_word:
            return False
    return True
```

## 2. 함수 연습 - rank
```python
def get_ranks(scores):
    ranks = []
    for score in scores:
        rank = 1
        for score_cmp in scores:
            if score < score_cmp:
                rank = rank + 1
        ranks.append(rank)
    return ranks 
```

## 3. Bubble sort
- 숫자들을 오름차순으로 정렬하는 (즉, sorting 하는) 알고리즘중 하나인 Bubble sort를 구현해 보자.
- **input**: unsorted list
- **output**: sorted list
- sol
    ```python
    def bubble_sort(lst):
        for stage in range(0, len(lst)):
            # lst[0: len(lst) - stage] 의 범위 내의 최대값을, 
            # lst[len(lst) - stage - 1] 에 넣는 것이 목표.

            for j in range(0, len(lst) - stage - 1):
                # j는 현재 window의 왼쪽 위치(index)를 의미한다.

                if lst[j] > lst[j + 1]:
                    # Swap lst[j] and lst[j + 1]
                    lst_j = lst[j]
                    lst[j] = lst[j + 1]
                    lst[j + 1] = lst_j
        return lst

    lst = [2, 3, 6, 2, -1, 0, 6, 2, 3]
    sorted_lst = bubble_sort(lst)
    print(sorted_lst)
    ```
    출력 결과
    ```
    [-1, 0, 2, 2, 2, 3, 3, 6, 6]
    ```

## 4. Insertion sort 짜기
- input: unsorted list
- output: sorted list
- sol
    ```python
    def insertion_sort(lst):
        for rnd in range(0, len(lst)):
            # Current rnd (round) 에서는
            # - lst[0: rnd] 가 현재로서는 sorted array이고
            # - lst[0: rnd + 1] 을 sorted array로 만들 예정이다.

            # sorted array에 새로 insert 할 target
            target_to_put_in = lst[rnd]

            # target_to_put_in 을 lst[0: rnd] 안에 잘 넣는다.
            # target을 앞 원소부터 비교해가며, 삽입할 위치를 찾는다.
            for j in range(0, rnd):

                # 삽입할 위치 확인 시
                if lst[j] > target_to_put_in:

                    # lst[j: rnd]를 한 칸씩 오른쪽으로 밀기
                    for k in range(rnd, j, -1):
                        lst[k] = lst[k - 1]

                    # 마지막으로 lst[j]에 target_to_put_in을 넣기
                    lst[j] = target_to_put_in

                    # 이번 라운드는 끝!
                    break

        return lst

    lst = [2, 3, 6, 2, -1, 0, 6, 2, 3]
    sorted_lst = insertion_sort(lst)
    print(sorted_lst)
    ```
    출력 결과
    ```
    [-1, 0, 2, 2, 2, 3, 3, 6, 6]
    ```
