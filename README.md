<details>
<summary>Tutorial 8</summary>

a. what is amqp? 

Jawab : AMQP adalah singkatan dari Advanced Message Queuing Protocol. Ini adalah protokol lapisan aplikasi standar terbuka untuk middleware yang memiliki orientasi pesan. Ini memungkinkan aplikasi untuk berkomunikasi satu sama lain secara asinkron yang dapat diandalkan dan aman, dengan melewati pesan melalui broker.

b. what it means? guest:guest@localhost:5672 , what is the first quest, and what is the second guest, and what is localhost:5672 is for?

Jawab : "guest" pertama menunjukkan nama pengguna yang digunakan untuk diautentikasi dengan broker pesan. "guest" kedua menunjukkan kata sandi yang digunakan untuk otentikasi. "localhost:5672" menunjukkan alamat dan port broker pesan. "localhost" merujuk pada mesin lokal, dan "5672" adalah port default untuk komunikasi AMQP. Jadi, alamat ini menunjukkan bahwa broker pesan sedang berjalan di mesin lokal dan mendengarkan koneksi pada port 5672.

<a href="https://ibb.co/GRQCSct"><img src="https://i.ibb.co/rH25r4c/Rabbit-MQ-Slow-Subscriber.png" alt="Rabbit-MQ-Slow-Subscriber" border="0"></a>

simulating slow subscriber, queuenya sekitar 20 keatas, queuenya ada 20 keatas karena dijalankan 6 kali cargo run pada publisher, oleh karena itu ada beberapa yang masih masuk queue.

</details>