# Mission 3

## Parts 1 & 2

[Link to video](https://youtu.be/Fv1vuObN7bc)

## Parts 3

Получить список юзернеймов пользователей

```select username from users;```

Получить кол-во отправленных сообщений каждым пользователем

```select "from", count(*) as message_count from messages group by "from";```

Получить пользователя с самым большим кол-вом полученных сообщений и само количество

```select u.id, count(m.id) as message_count from users u join messages m on u.id = m."from" group by u.id order by message_count desc limit 1;```

Получить среднее кол-во сообщений, отправленное каждым пользователем

```select avg(messages_count) as average_messages from (select count(id) as messages_count from messages group by "from") as message_counts;```
