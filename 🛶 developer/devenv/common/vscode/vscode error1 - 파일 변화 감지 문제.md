
# Trouble Shooting
## 큰 작업영역(Workspace)로 파일 변화를 감지 못 한다는 내용의 에러가 발생하는 경우 다음 명령어를 실행한다.
```
sudo vi /etc/sysctl.confg
```
* `G → i` 를 입력한 이후 다음을 타이핑한다. 
```
fs.inotify.max_user_watches=524288
```
* 종료는 `:wq`를 타이핑한 후 엔터키를 누르면 저장 종료한다. 
* 이후 다음 명령어를 기입하여 환경을 갱신한다. 
```
sudo sysctl -p
```