# Dokumentasi Modul `validate.js`
Modul `validate.js` pada library croot.js berfungsi untuk melakukan validasi input data pada sisi klien (client-side). Salah satu fungsi paling krusial adalah isEmail, yang berfungsi untuk memvalidasi apakah format string yang dimasukkan oleh pengguna merupakan alamat email yang sah atau tidak. Modul ini memastikan data yang dimasukkan pengguna sudah sesuai format sebelum diproses oleh sistem atau dikirim ke database. 

# Cara Penggunaan (Import)
import fungsii dari CDN jsDelivr ke dalam file JavaScript kamu yang bertipe `module`.

```javascript
import { isEmail } from "https://cdn.jsdelivr.net/gh/jscroot/lib@0.0.1/validate.js";
```

# Deskripsi Fungsi
`isEmail(value)`
Fungsi ini melakukan pengecekan string menggunakan Regular Expression (Regex) standar internasional untuk format email.

* Parameter: `value` (String) - Alamat email yang akan diperiksa
* Output: Jika string mengandung karakter @, nama domain, dan ekstensi domain yang valid maka `true` (contoh: user@gmail.com),Jika string tidak memenuhi kriteria email maka `false` (contoh: user@gmail, usergmail.com, atau hanya user).
 
 # Contoh Implementasi
 Kamu bisa menerapkan fungsi ini pada sebuah form login atau registrasi untuk memberikan peringatan kepada pengguna secara langsung.

### HTML

 ```html
<input type="email" id="emailUser" placeholder="Masukkan Email Anda">
<button onclick="cekValidasi()">Cek Email</button>
<p id="pesanError" style="color: red;"></p>
```
### JavaScript

```javascript
import { isEmail } from "https://cdn.jsdelivr.net/gh/jscroot/lib@0.0.1/validate.js";

window.cekValidasi = () => {
    const emailValue = document.getElementById("emailUser").value;
    const info = document.getElementById("pesanError");

    if (isEmail(emailValue)) {
        info.style.color = "green";
        info.innerText = "Email valid dan siap digunakan!";
    } else {
        info.style.color = "red";
        info.innerText = "Format email salah. Pastikan menggunakan @ dan domain yang benar.";
    }
};
```

# Kegunaan Utama
* Mencegah pengiriman data yang salah ke database.
* Memberikan pengalaman pengguna (User Experience) yang lebih baik dengan peringatan instan.
* Memastikan integritas data pada sistem komunikasi email.

