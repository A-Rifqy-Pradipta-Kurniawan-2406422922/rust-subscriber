# Subscriber - Tutorial A Checkpoint 2

> 1) Apa itu AMQP?

AMQP (Advanced Message Queuing Protocol) adalah protokol standar untuk sistem pesan (messaging) yang memungkinkan komunikasi andal antar aplikasi melalui message broker, seperti RabbitMQ.

> 2) Apa arti `amqp://guest:guest@localhost:5672`?

- `amqp://` = skema protokol AMQP
- `guest` pertama = username
- `guest` kedua = password
- `localhost` = host broker (berjalan di mesin yang sama)
- `5672` = port AMQP yang digunakan klien RabbitMQ
