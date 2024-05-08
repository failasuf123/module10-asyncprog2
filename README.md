"# module10-asyncprog1" 

1. Screen Shoot Output
![Gambar1.1](static/ssone.png)
- Program ini mengimplementasikan executor sederhana dengan spawner untuk mengelola dan menjalankan futures di Rust menggunakan lib futures. Ini adalah bagian dari pengembangan asynchronous programming di Rust.

- Yang terjadi adalah Sendy's Komputer: done! sedikit terlambat untuk dieksekusi karena menunggu asynchronous. Ini terjadi karena kode asyncronous menggunakan TimerFuture::new(Duration::new(2, 0)).await, yang artinya program akan menunggu selama 2 detik sebelum melanjutkan eksekusi setelah baris tersebut. Ini adalah sifat dari asynchronous programming di mana program dapat melanjutkan eksekusi selama menunggu operasi asynchronous selesai.

