# FTP Download  try typing a little faster next time

 작업환경 python3.7.3 

라이브러리 ftplib

ftplib 로 커낵션을 하고 

ftp connection을 열고 한동안 작업이 없을 경우 커낵션이 끊어지는 에러임

즉 Connection pool 이 발생하는 현상이다

굳이 ftp가 아니더라도 http나, database에서 자주 등장하는 에러 중 하나다.



- 가장 효율적인 방법은 connection time이 끊어지기 전에 무언가 작업을 수행하는 방법.
- connection 시간을 늘려주는 방법 ( 서버에서 제어하면 의미가 없음)



시도해 볼 만한 방법

- PASV 모드로 다운로드 하는 방식