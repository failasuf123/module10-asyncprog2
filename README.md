"# module10-asyncprog1" 

**1.2 Understanding how it works.**

![Gambar1.2](static/ssone.png)
- Program ini mengimplementasikan executor sederhana dengan spawner untuk mengelola dan menjalankan futures di Rust menggunakan lib futures. Ini adalah bagian dari pengembangan asynchronous programming di Rust.

- Yang terjadi adalah Sendy's Komputer: done! sedikit terlambat untuk dieksekusi karena menunggu asynchronous. Ini terjadi karena kode asyncronous menggunakan TimerFuture::new(Duration::new(2, 0)).await, yang artinya program akan menunggu selama 2 detik sebelum melanjutkan eksekusi setelah baris tersebut. Ini adalah sifat dari asynchronous programming di mana program dapat melanjutkan eksekusi selama menunggu operasi asynchronous selesai.


__1.3 Multiple Spawn and removing drop__

![Gambar1.2](static/1cMultipleAndSapwnRemove.png)

- Dengan menambahkan dua task tambahan,kita membuat program untuk menjalankan tiga operasi asynchronous secara konkuren. Masing-masing task mencetak "Sendy's Komputer: howdy!", "Sendy's Komputer: howdy2!", dan "Sendy's Komputer: howdy3!" sebelum menunggu selama 2 detik dan mencetak "Sendy's Komputer: done!", "Sendy's Komputer: done2!", dan "Sendy's Komputer: done3!" secara berturut-turut setelahnya.

- Dengan menghapus baris drop(spawner), kita tidak lagi memberi tahu executor bahwa tidak ada task baru yang akan dijadwalkan. Ini berarti executor akan terus berjalan dan menunggu task baru untuk dijalankan. Karena itu, executor akan menjalankan semua task yang sudah dijadwalkan (tiga task yang Anda spawn) sebelum akhirnya selesai dan program selesai berjalan.