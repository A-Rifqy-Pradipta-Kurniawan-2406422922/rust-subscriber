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

## Running at Least Three Subscribers

![/3-subs-RabbitMQ](./images/3-subscriber-RabbitMQ.png)

![/3-subs-terminal](./images/3-subscriber-terminal.png)

Berdasarkan gambar pertama tersebut, terlihat bahwa _queue_ dikonsumsi dengan kecepatan yang jauh lebih tinggi karena terdapat tiga konsumer (_subscriber_) yang secara bersamaan mengambil pesan dari _queue_, sehingga jumlah pesan dalam antrian berkurang secara signifikan. Pada gambar kedua, dapat diamati bahwa _message broker_ berhasil menyeimbangkan beban dengan mendistribusikan pesan-pesan kepada ketiga konsumer secara merata, di mana setiap konsumer menerima pesan yang berbeda-beda dan pesan yang telah diambil akan dihapus dari _queue_.
