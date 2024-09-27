**Selects**

`SELECT username
FROM users;`

`SELECT users.username, COUNT(messages.id) AS number_of_sent_messages
FROM users 
LEFT JOIN messages ON users.id = messages.from
GROUP BY users.username;`

`SELECT users.username, COUNT(messages.id) AS number_of_received_messages
FROM users
LEFT JOIN messages ON users.id = messages.to
GROUP BY users.username
ORDER BY number_of_received_messages DESC
LIMIT 1;`

`SELECT AVG(sent_messages) AS average_sent_messages
FROM (
    SELECT COUNT(messages.id) AS sent_messages
    FROM users
    LEFT JOIN messages ON users.id = messages.from
    GROUP BY users.id
) AS message_counts;`
