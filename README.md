# Subscriber - Tutorial A Checkpoint 2

> 1) Apa itu AMQP?

AMQP (Advanced Message Queuing Protocol) adalah protokol standar untuk sistem pesan (messaging) yang memungkinkan komunikasi andal antar aplikasi melalui message broker, seperti RabbitMQ.

> 2) Apa arti `amqp://guest:guest@localhost:5672`?

- `amqp://` = skema protokol AMQP
- `guest` pertama = username
- `guest` kedua = password
- `localhost` = host broker (berjalan di mesin yang sama)
- `5672` = port AMQP yang digunakan klien RabbitMQ

## Simulation Slow Subscriber

![/slow-RabbitMQ](./images/slow-RabbitMQ.png)

Pada gambar tersebut, terlihat ada pesan yang menumpuk dalam _queue_ karena subscriber membutuhkan waktu yang lebih lama untuk memproses setiap event dibandingkan dengan kecepatan publisher dalam mengirimkan pesan. Penumpukan ini terjadi karena ketidakseimbangan antara kecepatan produksi dan konsumsi pesan dalam sistem _message broker_.
