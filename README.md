# How to install Docker on MacOS and execute ubuntu

[Docker의 개념](https://subicura.com/2017/01/19/docker-guide-for-beginners-1.html) 을 먼저 읽는것이 도움이 될 듯하다.   
도커 설치는 다음 사이트에서 설치가 가능하다.
- [MacOS](https://hub.docker.com/editions/community/docker-ce-desktop-mac)
- [Windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
#
<위 과정에서 필요한 명령어>
    
**Docker가 잘 설치되었는지 확인**

```docker run hello-world```

아마 처음 설치를했다면 hello-world 라는 이미지가 없어서, docker가 없는걸 확인 후 자동으로 이미지 pull을 해와서 실행할것이다. 

<img width="1515" alt="Screen Shot 2021-09-07 at 10 36 28 PM" src="https://user-images.githubusercontent.com/84657474/132354176-75614003-29c9-4f1a-b917-6bc6f92537ec.png">
<hr>

# Ubuntu Image Install and bash run
```docker run -i -t --name Syno ubuntu /bin/bash```

Ubuntu의 Image를 가져와서 Syno라는 컨테이너를 생성하고 실행된다는 뜻입니다.   
만약 (--name Syno)를 생략하게된다면 Docker가 자동으로 컨테이너에 이름을 지정해줍니다.    
( -i : interactive /. t : Pseudo-tty )

<img width="1263" alt="Screen Shot 2021-09-07 at 10 42 22 PM" src="https://user-images.githubusercontent.com/84657474/132355171-e6d2598c-53df-4565-93d2-e54c224baf63.png">

이런식으로 Docker 의 Dashboard를 눌러보면 Syno라는 Ubuntu Image르 pull한 컨테이너가 생성되었고 실행중인 모습을 볼 수 있습니다.    
종료를 하고 싶다면 **exit** 를 입력하면 bash shell 에서 빠져나오게되고, Ubuntu Image에서 **/bin/bash** 에서 실행했기 때문에 여기서 빠져나오면 컨테이너가 정지 됩니다.

<img width="1158" alt="Screen Shot 2021-09-07 at 10 45 08 PM" src="https://user-images.githubusercontent.com/84657474/132355536-5f8ebbda-f706-48d6-bd25-c54a0fddd378.png">

# 기타 기억하면 좋은 명령어들
- 실행, 재시작, 정지   
```sudo docker start Syno //정지되 컨테이너 실행```   
```sudo docker restart Syno //재부팅한것처럼 다시 실행```    
```sudo docker attach Syno //시작한 컨테이너에 접속 -> 엔터 한 번 더 입력하면 bash shell 표시됨```    
```sudo docker stop Syno //컨테이너 정지```

- 목록 출력    
```sudo docker ps //실행중인 컨테이너 출력```   
```sudo docker ps -a //정지된 컨테이너까지 모두 출력```   
```sudo docker images //받은 이미지의 목록 출력```

- 삭제 제거   
```sudo docker rm Syno //컨테이너 삭제```    
```sudo docker rmi Ubuntu //이미지 삭제```

- 검색 docker search    
```sudo docker search ubuntu```
