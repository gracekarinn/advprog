**Refleksi commit 1:**

Code ini membangun web server sederhana yang menerima request HTTP, membacanya menggunakan `BufReader`, dan mencetaknya ke console. Namun, kode ini belum mengembalikan response kepada client. Dalam kelas, dijelaskan bahwa Rust memiliki keunikan seperti ownership dan error handling yang lebih ketat dibandingkan bahasa lain. 

**Refleksi commit 2:**

![Commit 2 screen capture](/assets/images/commit2.png)

Kode ini adalah HTTP server sederhana di Rust yang menangani request pada port `7878`, membaca request dengan `BufReader`, dan mengembalikan file `hello.html` sebagai respons dengan status `200 OK`.  

