**Refleksi commit 1:**

Code ini membangun web server sederhana yang menerima request HTTP, membacanya menggunakan `BufReader`, dan mencetaknya ke console. Namun, kode ini belum mengembalikan response kepada client. Dalam kelas, dijelaskan bahwa Rust memiliki keunikan seperti ownership dan error handling yang lebih ketat dibandingkan bahasa lain. 

**Refleksi commit 2:**

![Commit 2 screen capture](/assets/images/commit2.png)

Kode ini adalah HTTP server sederhana di Rust yang menangani request pada port `7878`, membaca request dengan `BufReader`, dan mengembalikan file `hello.html` sebagai respons dengan status `200 OK`.  

**Refleksi commit 3:**

![Commit 3 screen capture](/assets/images/commit3.png)

Saya telah mengikuti panduan tentang routing untuk halaman yang tidak dikenali, termasuk pembuatan halaman 404. Buku yang digunakan sangat jelas dan membantu sehingga saya semakin memahami sintaks serta gaya pemrograman Rust. Alur kode terasa jelas dan memudahkan saya dalam memahami cara kerjanya. 


**Refleksi commit 4:**

Code ini adalah web server single-threaded yang memproses request secara berurutan sehingga jika ada request lambat seperti `/sleep` seluruh server akan terblokir. Kekurangan utamanya adalah blocking execution, minimnya error handling, dan parsing HTTP yang terbatas. 


**Refleksi commit 5:**

Saya telah mengimplementasikan ThreadPool untuk menangani koneksi secara konkuren. Sekarang server dapat menangani beberapa request secara bersamaan tanpa terblokir oleh request yang membutuhkan waktu lama (seperti endpoint `/sleep`). Implementasi menggunakan konsep Rust seperti channels, mutex, dan Arc untuk berbagi data antar thread dengan aman. Pola "worker" yang digunakan memungkinkan server untuk mendistribusikan beban kerja secara efisien ke sejumlah thread yang telah ditentukan. Saya juga menambahkan implementasi trait Drop untuk memastikan shutdown yang bersih ketika server dihentikan. Dengan perubahan ini, performa server meningkat signifikan untuk menangani traffic yang lebih besar.