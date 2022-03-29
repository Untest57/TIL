## git 프로젝트 시작

### github 나 git 서비스 에서 저장소 생성

```shell
$ git clone {URL} [디렉토리 이름-기본값: 저장소 이름]
```

### git init

```shell
$ mkdir {저장소 이름}
$ cd {저장소 이름}
$ git init

// git 서비스에서 빈 저장소 생성
$ git remote add origin {저장소URL}

//README.md 추가시
$ touch README.md
$ vi README.md
$ git add README.md
$ git commit -m "docs: Create README.md"

$ git push -u origin master
```
