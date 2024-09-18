
## 기본 설치 

- **기본 편집기 설치**   


```shell
bash  sudo apt install vim
```


- **관리자 계정 설정을 위한 프로그램 설치**bash
    

```shell
sudo apt install sudo
```
`
    
- **계정 추가**bash
    

```bash
adduser 계정명
```

    
- **`visudo`를 사용하여 사용자에 sudo 권한 추가**bash
    

```bash
visudo
```

    
- **소스코드 관리를 위한 프로그램 설치**bash
    

```shell
sudo apt install git gitflow
```

    
- **한국어 locale 설정**
    
    

```bash
sudo apt-get install language-pack-ko 
sudo locale-gen ko_KR.UTF-8 
sudo dpkg-reconfigure locales 
sudo update-locale LANG=ko_KR.UTF-8 LC_MESSAGES=POSIX
```

## SSH 설정

- **SSH 서버 설치**
    

```bash
sudo apt install openssh-server
```

    
- **root의 `.bashrc` 마지막에 SSH 서비스 시작 추가**bash
    

```bash
echo "service ssh start" >> ~/.bashrc
```
