---
title: [확률 및 통계] 조건부확률과 Bayes 정리
date:   2020-07-23 23:26:00
categories: probability bayes
---

# 조건부확률과 Bayes 정리

## 0. Introduction: Probability
유튜브 강의에서는 나와있지 않지만, 강의자료에 간략히 적혀 있습니다.
1. Probability
    - What? Why? When or Where? How?
2. Statistics
    - What? Why? When or Where? How?

## 1. Basic Probability Concepts

1. Sample Space S(set)
    - Sample Space는 가능한 모든 경우의 전체 집합이다
    - 확률 공간을 다루는데 있어서 전제조건이 된다
    - Sample Space를 벗어나는 것은 생각할 필요 없음

2. Event (A)
    - Sample Space의 부분집합 A ⊂ S
    - P(A) = prob(outcome∈A)
        - P(A)는 어떤 결과가 A라고 하는 집합에 속할 확률

3. Conditional Probabilirt
    - P(B|A)
        - A라는 condition이 발생했을 때, B라는 이벤트가 발생하게될 확률
        - = P(B∩A)/P(A)
        - 어떤 시행을 거쳐서 얻게 되는 Sample Space라는 Condition이 있고, A와 B가 동시에 발생할 확률
            - Sample Space는 굳이 condition 파트에 넣지 않음

    - case 예시
        - P(today's wheather | yester day's wheather, 2-days ago wheather, ... )
            - 조건부확률은 전제를 갖고, 원하는 이벤트의 발생 확률이 얼마나 되는가?
            - 기존의 전제가 이벤트에 얼마나 관련이 있는지 따지는 것이 조건부 확률

4. Total Probability
    - P(A) = P(A1) + P(A2) + ... + P(An)
        - 서로 중복이 되지 않는 여러 배반사건들의 확률의 합으로 event A의 확률을 구하는 것을 total probability라고 함
        - {A1, A2, ..., An} : Partition of A
        - P(A1) = P(A1∩A) = P(A|A1)P(A1)
        - P(A) = ∑P(A|Ai)P(Ai)
    - priori: 사전에 알고 있는 조건부 확률

5. Bayes' Theorem
    - P(B|A) = P(B∩A)/P(A) = P(A|B)P(B)/P(A)
        - P(B|A)를 단번에 구할 수 없는 경우, 혹은 어려운 경우 그 둘의 순서를 바꾸어서 구할 수 있도록 하는 것
        - P(A|B)가 이미 알려진 priori가 되어야함!
    - P(Ai|A)
        - A라는 전체가 발생했을 때, 일부분에 해당하는 Ai는 얼마가 되는가? 라는 비율을 따지는 문제가 될 수 있음
        - 앞에서처럼 사전에 알려질만한 확률값으로 바꾸어보자
        - P(A|Ai)P(Ai)/P(A)
        - A라는 결과가 Ai로부터 오게된 것인지 아닌지 가능성을 계산해보는 것 (여기서 A는 observation data(관측한 데이터), Ai는 unknown input)
        - example 1.7) Binary Symmetric Channel               
    - 이런식으로 조건의 위치를 서로 바꿔가면서 문제를 푸는 수학적인 방법을 베이지안이라고 함

6. Independent Events
    - If A and B are mutually independent
        - P(B|A)는 P(B)와 상관 없다
        - A가 발생하는 것은 B가 발생하는 것에는 아무런 영향을 주지 않는다.
        - P(B)=P(A∩B)/(A) 이므로, P(A∩B)=P(A)P(B)를 증명하면, A와 B가 서로 독립이다.
    - example
        - repeated restored trials
            - 매번 동일한 조건이어야 하기 때문에, 복원 시행(restored trials) 이라고 한다.
            - 예를들어 주사위를 굴리는 것처럼 독립적인 것
            - 고등학생 때 풀던 문제를 예를들면,
                - 빨간색 공과 흰색 공이 들어있는 주머니에서 공을 꺼낼 경우 빨간색이 나올 확률은?
                    - 뽑은 공을 다시 집어 넣으면, 복원을 해준 것. 독립!
                    - 뽑을 공을 다시 집어 넣지 않고, 다음 공을 꺼낼 경우는 복원하지 않은 것. 독립이 아님!
    - independent ≠ exclusive
        - independent: 서로 상관성이 없다. 영향을 주지 않는다.
        - exclusive: 서로 공통된 요소가 없다. 즉, 교집합이 없다고 해서 서로간에 영향을 주지 않는 것은 아님.
        - 둘은 다른 의미의 말!
    -If A and B are (mutually) independent
        - A와 B의compliment, A의 compliment와 B, A의 compliment와 not B는 각각 독립관계이다.

7. Combined Experiments
    - 2가지 이상의 시행을 하는 것
        - ex) 동전을 한 번 던지는 것은 Sample Space가 앞면과 뒷면, 딱 두가지만 있음
        - ex) 동전을 두 번 던지는 것은 앞앞, 앞뒤, 뒤앞, 뒤뒤와 같이 각각의 Sample Space로부터 조합이 생김
    - for two experiments with S1, S2
        - S = S1 X S2
            - 여기서 X는 cartesian Product라고 함.
            - cartesian은 순서쌍을 만들어주는 것을 말함
            - { (xi, yi) | xi∈S1, yi∈S2 }
            

첫 post이기 때문에, 아래의 예를 포함합니다.

## Table을 작성하는 예

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |


## Code를 작성하는 예

{% highlight python %}
class node:
    def __init__(self, data, next=None):
        self.data = data
        self.next = next
{% endhighlight %}
