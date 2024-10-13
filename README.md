# SWE_2021_41_2024_2_week_6

---

## Week 4 Assignment

[Go to the Repository](https://github.com/Jinozzs/SWE_2021_41_2024_2_week_4.git)

```python
def isHappy(n):
    # 숫자의 각 자릿수의 제곱의 합을 계산하는 헬퍼 함수
    def get_next(number):
        total_sum = 0  # 자릿수의 제곱 합을 저장할 변수
        while number > 0:  # number가 0보다 클 때까지 반복
            digit = number % 10  # number의 마지막 자릿수 추출
            total_sum += digit ** 2  # 자릿수의 제곱을 합산
            number = number // 10  # number에서 마지막 자릿수를 제거
        return total_sum  # 모든 자릿수의 제곱 합 반환

    seen = set()  # 이미 처리한 숫자들을 저장할 집합(반복 여부 확인을 위함)
    
    # n이 1이 아니고, n이 이미 처리한 숫자에 포함되지 않을 때까지 반복
    while n != 1 and n not in seen:
        seen.add(n)  # 현재 숫자를 집합에 추가하여 나중에 반복 확인
        n = get_next(n)  # 다음 숫자를 계산 (현재 숫자의 자릿수 제곱 합)
    
    return n == 1  # n이 1이 되면 True 반환 (행복한 숫자), 그렇지 않으면 False 반환
```

---

## Week 5 Assignmnet

> ```
> docker exec <container_name> cat /etc/os-release
> ```
> Docker 컨테이너에서 /etc/os-release 파일의 내용을 출력 |
> → 컨테이너의 운영체제에 대한 정보(이름, 버전 등)를 표시

> ```
> docker exec <container_name> git --version
> ```
> Docker 컨테이너에서 git 버전을 확인 |
> → git version 2.43.0

> ```
> docker exec <container_name> python3 --version
> ```
> Docker 컨테이너에서 python3의 버전을 확인 |
> → Python 3.12.3

> ```
> docker inspect --format="{{ .HostConfig.Binds }}" <container_name>
> ```
> 특정 Docker 컨테이너의 볼륨 바인딩 정보를 확인 |
> 컨테이너가 호스트 시스템과 어떤 디렉토리를 공유하고 있는지 보여줌 |
> → [/home/sy2018314609/ossp_host_dir:/mnt/ossp_container_dir]
