github 관련된 문서
===

## markdown 문법
* 참고
    - https://gist.github.com/ihoneymon/652be052a0727ad59601
    - https://alwaysone.tistory.com/entry/Github-알아보기-마크다운을-사용하여-문서-작성하기

## vscode 에서 github repository 생성
1. vscode 에서 폴더 생성
2. vscode terminal 열어서
3. git 초기화
```
% git init
```
4. git 환경설정
```
% git config --global user.name <계정명>
% git config --global user.email <계정이메일>
```
5. source control tab 에서 publish to github
6. public repository 선택해주면
7. 해당 폴더명을 repository 생성 완료
* 참고 
    - https://artistjay.tistory.com/72
    - https://velog.io/@blair-lee/VSCode에서-Github-업로드하는-방법짱쉬움ㅋㅋ

## github로 홈페이지 만들기
1. vscode 에서 폴더 하나 만들어서 index.html (테스트용) 생성
    - 폴더명과 repository는 같게 하면 편함

2. git init, config 후 publish(commit)
    + **_repository 생성 - vscode로 해도 됨_**
    - repository를 **id.github.io**로 만들면 https://id.github.io
    - repository를 **sub 폴더명**으로 만들면 https://id.github.io/sub
3. github.com 로그인 해서 해당 repository - setting - pages
    - Branch - main /(root) 선택 후 save
4. id.github.io 해당 주소로 브라우저에서 접속
    - 5분 정도 걸릴 수 있음
    - 수정은 1분 정도 걸림
    - 기존 캐시가 있을 경우는 browser update가 안 될 수 있으니 다른 브라우저로 시도
* 참고
    - https://brunch.co.kr/@topasvga/2278