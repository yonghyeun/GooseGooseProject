# GooseGooseProject

![mbBFUrshAIo_XJnGOoU9POA3aF2r3fwSfV7ljxfY3kqzI4T9CBvHsQwK8jn9_DSCpnnWwAPrzuVJw6PM-6C-dw](https://github.com/yonghyeun/GooseGooseProject/assets/123540354/beeac4e3-2080-4aa8-b8a4-4a6b1681f7ce)


# 프로젝트 개요

<aside>
💡  Goose Goose Duck은 인기 있는 게임인 어몽 어스(Among Us)와 플레이 방식이 유사한 멀티플레이어 비디오 게임입니다. 이 게임은 독립 개발자 팀이 개발했으며 2020년 말에 출시되었습니다.

 게임에서 플레이어는 우주선의 승무원 또는 사기꾼의 역할을 맡습니다. 승무원의 목표는 사기꾼을 식별하고 투표하는 반면 사기꾼은 승무원을 방해하고 나머지 플레이어와 섞이려고 합니다. 이 게임은 라운드로 진행되며 각 라운드가 끝날 때 플레이어는 사기꾼이 누구라고 생각하는지 투표할 수 있습니다.

</aside>

 나는 몇 판째 해도 오리가 걸리지 않는데 그럴 확률은 얼마나 되고 나보다 운이 좋은 사람들은 내 앞에 몇 명이나 있을까? 과연  몇 판이나 해야 내가 오리에 한 번 걸릴 수 있을까?

 게임을 하다 보면 몇 판 연속 한 것 같은데 어떤 사람만 계속 오리 역할이 걸리는 것만 같고, 나는 아무리 해도 오리가 걸리지 않는 듯한 느낌이 든다. 혹은 어느정도 오리가 걸리지 않았다면, 이제 슬슬 확률적으로 내가 오리가 걸릴 때가 되었다는 느낌이 들 때가 있다. 

 그럴 때의 확률값을 확률론적으로 알아보고 같은 게임을 하는 참가자들에게 알려주는 것이 주 목표이다.

# 이론적 배경

### 오리가 걸릴 확률

 구스구스덕은 최소 6명이 모여야 게임을 시작 할 수 있으며 오리의 수는 6명일 경우엔 1명, 10명 이상일 경우엔 2명이 선택 될 수 있다. 즉 오리가 걸릴 확률은 10명 이하 일 경우엔 1/n , 10명 이상일 경우엔 2/n 이다. 
 

$$
P = \frac{d}{n},\ d=\begin{cases}    1 & \text{if } n<10 \\    2 & \text{if } n\geq10\end{cases}
$$

 각 판에서 오리가 걸릴 확률은 전 사건에 영향을 주지 않으며 매 판 독립적이다. 즉 오리가 걸릴 확률은 베르누이 시행이다.

 

$$
p_1,p_2,...,p_n \overset{iid}{\sim} \text{Bernoulli}(\frac{d}{n}), d=\begin{cases}    1 & \text{if } n<10 \\    2 & \text{if } n\geq10\end{cases}
$$

### 게임을 m판 하였을 때 오리가 k번 걸릴 확률

$$
P(X=k) = {m\choose k} p^k (1-p)^{m-k}
$$

 오리가 걸릴 확률은 베르누이 시행을 따르는 확률 P이기 때문에 게임을 m판 하였을 때 오리가 k 번 걸릴 확률은 이항 분포를 따른다.

### 오리가 k 번 걸리기 위해 시행해야 하는 게임 횟수

$$
P(X=m) = {m-1 \choose k-1} p^k (1-p)^{m-k}
$$

 

오리가 k번 걸리기 위해 시행 해야하는 게임 횟수는 음이항 분포를 따른다. 마지막 게임엔 무조건 오리가 나와야 하니 m-1 번째 사건까지 k-1 번 성공하고 마지막 게임에서는 오리가 걸리면 되기 때문이다.