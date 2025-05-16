### 1. How much data your publisher program will send to the message broker in one run?
> Dalam satu kali run, program publisher akan mengirim data ke message broker sebesar sekitar 16 byte, tergantung isi field user_id dan user_name. Data ini diserialisasi menggunakan Borsh, yang menyertakan panjang string dan isi string itu sendiri, sehingga ukuran total bergantung pada panjang teks yang dikirim.

### 2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
> amqp://guest:guest@localhost:5672 yang digunakan baik di program publisher maupun subscriber menunjukkan bahwa keduanya terhubung ke message broker yang sama, yaitu RabbitMQ yang berjalan di localhost pada port 5672, dengan kredensial default guest sebagai username dan password. Ini memungkinkan kedua program saling bertukar pesan melalui broker yang sama.

### Screenshot RabbitMQ
![ss-rabbitmq](assets/images/ss-rabbitmq.png)

### Console After Running `cargo run`
![ss-subscriber](assets/images/ss-subscriber-console.png)
![ss-publisher](assets/images/ss-publisher-console.png)
> Berdasarkan log dari console subscriber, dapat terlihat bahwa terdapat setiap satu kali publisher dirun, maka terdapat 5 message yang dikirim melalui message broker dan ditangkap oleh subscriber.
