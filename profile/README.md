# 우테코 프리코스 나만의 풀이 저장소 

## 🤮 들어가기에 앞서서 - 포크한 레포지토리에 잔디 심기
>포크한 레포지토리에 커밋 작업을 진행해도 내 잔디는 심어지지 않는다.<br> 
> 그래서 나의 잔디 심기 작업을 위해서 fork 해온 repository에 commit 했을 때도 잔디가 잘 심어질 수 있게 선행 작업을 진행했다.<br>
> ✏ 참고: https://velog.io/@pgmjun/Git-Fork%ED%95%9C-%EB%A0%88%ED%8F%AC%EC%A7%80%ED%86%A0%EB%A6%AC%EC%9D%98-%EC%BB%A4%EB%B0%8B%EC%9D%84-%EC%9E%94%EB%94%94%EC%97%90-%EB%B0%98%EC%98%81%ED%95%98%EA%B3%A0-%EC%8B%B6%EB%8B%A4%EB%A9%B4-Git-Mirror-Push-feat.-%EC%9A%B0%ED%85%8C%EC%BD%94
### 간단 정리
Repository A를 Repository B로 옮기기
1. git bash를 연다
2. A를 clone받기
```
$ git clone --bare [A주소]
```
3. 폴더 이동하고 B에 푸시하기
```$ cd [A 폴더]
$ git push --mirror [B주소]
```
4. 임시 로컬 저장소 A를 지우기
```$ cd ..
$ rm -rf [A 폴더]
```

## 🧟‍♀️fork repository에 commit도 내 잔디로 가져오자
### 1. fork
![image](https://github.com/yalooWoowaPreCourse/.github/assets/81970382/0e22a3af-44ae-4d4a-99a2-499c707757d5)
![image](https://github.com/yalooWoowaPreCourse/.github/assets/81970382/36c9e2b4-1488-4edf-8fc4-be51573b16bc)
- fork repository 이름은 알아서 .. 
- fork repository를 생성해준다. 

### 2. fork한 레포지토리 clone
#### 2-1. git clone?
- `git clone [REPO_URL] [DIR]`의 경우엔 원격 Git 저장소를 복제할 때 사용합니다.
  - [REPO_URL] 클론해올 저장소의 주소를 지정
  - [DIR] 로컬에 복제할 위치를 지정합니다. 생략이 가능하며 특별한 이유가 없다면 보통 생략한다.

#### 2-2. fork해온 repository HTTPS를 복사해줍니다.
![image](https://github.com/yalooWoowaPreCourse/.github/assets/81970382/78b12c1d-316f-4101-93e5-f0cc98791104)

#### 2-3. 명령어를 사용해서 fork한 레포지토리를 로컬 환경에 clone bare 해줍니다.
```
$ git clone --bare 여기에 복사한 주소를 넣어주세요
```
```
[example]
$ git clone --bare https://github.com/yeomyaloo/java-lotto-6.git
```
![image](https://github.com/yalooWoowaPreCourse/.github/assets/81970382/004bd0fb-cb74-465e-88fd-88c0bb9ed840)

- 해당 명령어는 git bash를 사용해서 진행했기 때문에 있는 분들은 이렇게 진행하면 됩니다.
> git bash가 아닌 명령어를 사용해서 진행한다면?<br> 
> - 일단 Linux 명령어를 Windows 환경에서도 공통 사용하기 위해서 git bash를 사용하기 때문에 Windows 환경인 사람들은 다운 받아 사용하자 편리하다.<br>
> - 그렇지 않은 경우라면 원격 환경(=깃허브에 있는 내 레포지토리)에 연결 해둔 로컬 파일(=내 컴퓨터에 있는 폴더)에 위치로 가서 명령어 터미널을 열어서 `cd 로컬_파일_주소`를 치고 위의 clone --bare 명령어 작업을 진행합니다!

#### 2-4. git bash를 사용해 clone bare 작업
![image](https://github.com/yalooWoowaPreCourse/.github/assets/81970382/f537ca21-0066-4054-bfe6-d5d4a93c0480)

- 히스토리, 브랜치 정보만을 가지는 가벼운 복제본을 만들고 원격 저장소 백업, 공유 목적으로 사용된다.
### 3. 로컬 환경에 fork repository를 clone bare(얕은 복제)한 위치로 이동
![image](https://github.com/yalooWoowaPreCourse/.github/assets/81970382/a1313870-ea18-4fc3-8af3-cee1b4233fd6)

```
cd java-lotto-6.git
```
- 이동하기 전에는 main 브랜치에 있는 것을 확인할 수 있습니다.

### 4. Git Bare Repository
#### 4-1. clone --bare 한 디렉토리로 이동
![image](https://github.com/yalooWoowaPreCourse/.github/assets/81970382/66ee1ef3-926c-47c5-9992-e90ac3e50875)

- bare Repository로 이동 후 브랜치가 BARE:main인 것을 확인할 수 있습니다.

#### 4-2. push 할 나의 Repositorydp mirror 작업하기
```
$ git push --mirror https://github.com/userId/newRepo.git
```
- 이제 java-lotto-6에 있는 자료를 newRepo에 저장합니다.


