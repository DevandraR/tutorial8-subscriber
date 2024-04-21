<details>
<summary>Tutorial 8</summary>

a. what is amqp? 

Jawab : AMQP adalah singkatan dari Advanced Message Queuing Protocol. Ini adalah protokol lapisan aplikasi standar terbuka untuk middleware yang memiliki orientasi pesan. Ini memungkinkan aplikasi untuk berkomunikasi satu sama lain secara asinkron yang dapat diandalkan dan aman, dengan melewati pesan melalui broker.

b. what it means? guest:guest@localhost:5672 , what is the first quest, and what is the second guest, and what is localhost:5672 is for?

Jawab : "guest" pertama menunjukkan nama pengguna yang digunakan untuk diautentikasi dengan broker pesan. "guest" kedua menunjukkan kata sandi yang digunakan untuk otentikasi. "localhost:5672" menunjukkan alamat dan port broker pesan. "localhost" merujuk pada mesin lokal, dan "5672" adalah port default untuk komunikasi AMQP. Jadi, alamat ini menunjukkan bahwa broker pesan sedang berjalan di mesin lokal dan mendengarkan koneksi pada port 5672.

<a href="https://ibb.co/GRQCSct"><img src="https://i.ibb.co/rH25r4c/Rabbit-MQ-Slow-Subscriber.png" alt="Rabbit-MQ-Slow-Subscriber" border="0"></a>

simulating slow subscriber, queuenya sekitar 20 keatas, queuenya ada 20 keatas karena dijalankan 6 kali cargo run pada publisher, oleh karena itu ada beberapa yang masih masuk queue.

<a href="https://ibb.co/C2tGmfv"><img src="https://i.ibb.co/2N64WTP/Rabbit-MQ-Multiple-Subscriber.png" alt="Rabbit-MQ-Multiple-Subscriber" border="0"></a>

subscriber dijalankan pada 3 console sekaligus

<a href="https://ibb.co/6vXpjsQ"><img src="https://i.ibb.co/PTDbqCk/Rabbit-MQ-Run3-Subscriber.png" alt="Rabbit-MQ-Run3-Subscriber" border="0"></a>

hasil menjalankan 3 console subscriber sekaligus pada RabbitMQ, queue menjadi lebih cepat menurun karena 3 console yang dijalankan secara parallel dapat membagi message secara lebih efisien, sehingga tidak perlu queue yang banyak agar semua message bisa masuk.

untuk peningkatan yang harus ditambahkan pada kode :

1. Subscriber

Implementasikan metode get_handler_action : Pada implementasi UserCreatedHandler, terdapat metode get_handler_action yang saat ini menggunakan todo!(). Metode tersebut sebaiknya diimplementasikan.

Error Handling : Tambahkan Error handling untuk panggilan metode listen untuk menangani kemungkinan kesalahan dengan lebih baik. Misalnya, dapat menggunakan pernyataan match untuk menangani Result yang dikembalikan oleh listen.

Smooth finish : Pertimbangkan untuk mengimplementasikan cara untuk mengakhiri program secara mulus jika diperlukan. Saat ini, pernyataan loop menyebabkan program berjalan tanpa batas, yang mungkin tidak diinginkan dalam semua kasus.

2. Publisher

Error handling : Tambahkan error handling untuk panggilan metode publish_event untuk menangani kemungkinan kesalahan dengan lebih baik. Seperti halnya listener, dapat menggunakan pernyataan match untuk menangani Result yang dikembalikan oleh publish_event.

Publikasi Asynchronous: Pertimbangkan untuk membuat proses program menjadi asynchronous untuk menghindari bottleneck. Dapat menggunakan fitur async/await Rust bersama dengan runtime asynchronous seperti Tokio atau async-std untuk mencapainya.

Organisasi Kode: Pertimbangkan untuk menyusun kode ke dalam fungsi atau modul terpisah untuk meningkatkan kerapihan dan kemudahan pemeliharaan, terutama jika program berkembang menjadi lebih kompleks.

Dokumentasi: Tambahkan komentar dokumentasi yang sesuai (///) untuk mendokumentasikan tujuan dan penggunaan dari tipe, fungsi, dan metode. Ini akan membuat kode lebih mudah dimengerti bagi pengembang lain di masa depan.

</details>