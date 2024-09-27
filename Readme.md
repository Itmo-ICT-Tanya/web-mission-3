# Mission 3

## Part 1 [Link to video](https://disk.yandex.ru/i/oxP9K0_7qs4A2w)

## Part 2  [Link to video](https://disk.yandex.ru/i/PJ1WcGfTOvBbBg)

## Part 3

**Selects**

```sql SELECT username FROM users;```

```sql SELECT users.username, COUNT(messages.id) AS number_of_sent_messages FROM users  LEFT JOIN messages ON users.id = messages.from GROUP BY users.username;```

```sql SELECT users.username, COUNT(messages.id) AS number_of_received_messages FROM users LEFT JOIN messages ON users.id = messages.to GROUP BY users.username ORDER BY number_of_received_messages DESC LIMIT 1;```

```sql SELECT AVG(sent_messages) AS average_sent_messages FROM ( SELECT COUNT(messages.id) AS sent_messages FROM users LEFT JOIN messages ON users.id = messages.from GROUP BY users.id ) AS message_counts;```
