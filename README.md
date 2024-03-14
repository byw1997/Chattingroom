# Chattingroom
MultiuserChatting

Environment

-Windows11 Pro

-C++ Latest

-PostgreSQL 15.4


Requirements

-pqxx(C++ library)

-Need to create Database "host=localhost port=5432 dbname=serverpj user=dbadmin password=dbpassword" before test

-Need to update server ip address setting in client source code


.cpp route:Loginserver\loginserver\loginserver\loginserver.cpp, Client\client\client\client.cpp


Every commands are case-insensitive.

Server accepts at most MAX_USERS_ONLINE(default = 10) clients.

client tries to connect to server socket. If fail to connect, Enter R to retry, Enter E to exit.

If success to make connection, Enter signup to make account. Enter E to exit. Loop while input is Exit or success login.

If signup entered, Get ID, password, Nickname as input. Server checks ID, Nickname duplication by checking database. If more than 0 column checked, signup fails and notice client the reason why signup failed.

If login entered, Get ID, password as input. Check database and get column corresponding to the input. If none, login fails. And if the user_id in column corresponding to input already logged in, login fails.

If successfully logged in, client gets welcome message and recent 10 messages and get user command as input. These are user commands.

help: output help message

say <message>: send <message> to everyone (format: [YYYY-MM-DD HH:mm]nickname>> message)

whisper <target> <message>: send <message> to <target> (format: [YYYY-MM-DD HH:mm] (whisper)nickname>> message / [YYYY-MM-DD HH:mm] (whisper)nickname<< message)

users: output every user nickname currently logged in

exit: terminate

