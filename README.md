# Chattingroom
MultiuserChatting

Environment

-Windows11 Pro

-C++ Latest

-PostgreSQL 15.4


Requirements

-pqxx(C++ library)

-Need to create Database "host=localhost port=5432 dbname=serverpj user=dbadmin password=dbpassword" before test


.cpp 경로:Loginserver\loginserver\loginserver\loginserver.cpp, Client\client\client\client.cpp


서버는 최대 MAX_USERS_ONLINE(default = 10) 개의 클라이언트를 수용한다.

클라이언트는 첫 화면에서 서버와 연결을 시도하며, 실패시 R을 입력하여 재시도, E를 입력하여 종료할 수 있다.

연결 성공 시 login 을 입력하여 로그인 시도, signup을 입력하여 회원가입을 시도할 수 있다. exit을 입력 시 종료된다. exit이 입력되거나 login에 성공할 때까지 반복된다.

signup 입력 시 ID, password, Nickname을 입력받는다. ID, Nickname 중복 여부를 데이터베이스를 조회해 검사한다. 조회된 column 수가 0보다 클 경우 signup이 실패하며 클라이언트는 실패 사유를 전달받는다.

login 입력 시 ID, password를 입력받는다. 데이터베이스를 조회해 입력받은 정보와 일치하는지 검사한다. 일치하지 않으면 실패한다. 또한 접속중인 유저들의 user_id와 대조하여 이미 접속중일 시 실패한다.

login 성공 시 welcome message와 채팅방에 입력된 최근 10개의 채팅 내역을 출력하며 명령어를 입력받는다. 명령어는 다음과 같다.

help: 도움말 출력

say <message>: <message> 모두에게 전달 (format: [2024-3-11 18:10]nickname>> message)

whisper <target> <message>: <target>에게 <message> 전달 (format: [2024-3-11 18:10](whisper)nickname>> message / [2024-3-11 18:10](whisper)nickname<< message)

users: 현재 접속중인 유저 닉네임을 전부 출력

exit: 종료

