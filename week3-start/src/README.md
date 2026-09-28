# 3회차 과제

## Web Server의 두 가지 역할
(1) Web Server는 브라우저가 웹페이지를 표시하는데 필요한 정적 파일을 요청에 따라 전달한다. 이번 과제에서도 dist 폴더의 파일들을 nginx가 파일에 제공했으며, 해시를 활용하여 브라우저가 캐시에 저장된 파일을 매번 다운로드하는 대신 다시 사용할 수 있었다. 

(2) Web Server는 사용자가 어떤 URL로 요청을 보냈는지에 따라 적절한 응답을 결정한다. 이번 과제에서는 /about처럼 실제 파일이 없는 경로를 요청했을 때 try_files 설정에 따라 index.html 혹은 404 Not Found를 반환하도록 변경할 수 있었다. 또한 /healthz 경로에는 location = /healthz처럼 경로에 대한 규칙을 따로 지정해 nginx가 직접 정해진 응답을 반환하도록 실습을 진행했다. 이를 통해 요청 경로마다 서로 다른 처리 방식을 지정할 수 있다는 것을 이해했다.

## 필수 과제 1: nginx 설정 바꿔보기
(a) try_files의 마지막 값을 =404로 바꾸면 존재하지 않는 경로를 요청할 시 index.html 대신 404 Not Found를 반환한다.
<img width="374" height="167" alt="Screenshot 2026-09-28 at 8 46 58" src="https://github.com/user-attachments/assets/2535ba21-c5db-419c-857f-aca415834c9b" />
<img width="364" height="125" alt="Screenshot 2026-09-28 at 8 47 13" src="https://github.com/user-attachments/assets/ef354fa8-94f4-45a8-83c6-7ed1c66f7ece" />

(b) =는 요청 경로가 /healthz와 정확히 일치할 때만 해당 규칙을 적용한다는 의미이다.
<img width="284" height="135" alt="Screenshot 2026-09-28 at 12 53 31" src="https://github.com/user-attachments/assets/144d2a91-e9bd-4871-9928-13c771ce5d0e" />

---

## 필수 과제 2: 캐시 헤더 실험
(1,2)
<img width="1435" height="858" alt="Screenshot 2026-09-28 at 9 08 03" src="https://github.com/user-attachments/assets/939c721f-ebe2-4887-a387-48a7448c1915" />

(3)
<img width="368" height="322" alt="Screenshot 2026-09-28 at 11 48 56" src="https://github.com/user-attachments/assets/a590d83e-f260-4143-b33d-b514165c54ff" />

(4)
<img width="371" height="337" alt="Screenshot 2026-09-28 at 12 37 43" src="https://github.com/user-attachments/assets/a8cb58dd-3773-4dd3-a360-c85179f4815b" />

## Docker 웹페이지 캡쳐본
<img width="1438" height="856" alt="Screenshot 2026-09-28 at 12 54 55" src="https://github.com/user-attachments/assets/a88a7ab8-d3ee-4ade-97f8-6d7aa86c2be6" />
