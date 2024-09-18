

## Python 설정
- Windows 기본설정에서는 PowerShell의 기본설정 때문에 venv의 스크립트가 제대로 실행되지 않는다. 
- 이에 관리자 권한으로 PowerShell을 실행한 후 스크립트 실행권한을 변경한다. 
  ```
  Set-ExecutionPolicy RemoteSigned
  ``` 