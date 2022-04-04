# GIT 정리

## First Start

### Set configuration
```shell
$ git config --global user.name "{USERNAME}"
$ git config --global user.email "{EMAIL}"
$ git config --global core.editor "{vi|TEXT_EDITOR}"
//cli 내에서 당장 보려면 cat
$ git config --global core.pager "cat"
```

## [config](https://git-scm.com/docs/git-config)
### add
```shell
$ git config [--global] {변수명} {값}
```
### remove
```shell
$ git config [--global] --unset {변수명}
```
### 전부 보기
```shell
$ git config [--global] -l|--list
```
### [변수들](https://git-scm.com/docs/git-config#_variables)

## init
디렉토리에 저장소 생성
디렉토리에 저장소 여부는 .git 디렉토리

### 잘못된 저장소 제거

저장소 최상단에서
```shell
$ rm -rf .git
```

## [clone](https://git-scm.com/docs/git-clone)
```shell
$ git clone {URL} [디렉토리이름-기본값:저장소이름]
```

## add
```shell
$ git add []
```
