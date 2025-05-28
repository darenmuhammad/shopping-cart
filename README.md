# 📘 JavaScript Class Concepts

Dokumentasi singkat untuk memahami konsep-konsep penting dalam JavaScript OOP dan method bawaan.

## 🔹 `class`

`class` adalah blueprint atau cetakan untuk membuat objek.

```js
class Mobil {
  constructor(merk) {
    this.merk = merk;
  }

  jalan() {
    console.log(`${this.merk} sedang berjalan`);
  }
}
```

## 🔹 `constructor`

`constructor` adalah method khusus yang otomatis dijalankan saat objek dibuat. Biasanya digunakan untuk inisialisasi properti.

```js
class User {
  constructor(nama) {
    this.nama = nama;
  }
}
```

## 🔹 `this`

`this` mengacu pada instance dari class saat ini. Digunakan untuk mengakses properti atau method dari objek itu sendiri.

```js
class Produk {
  constructor(nama, harga) {
    this.nama = nama;
    this.harga = harga;
  }

  info() {
    console.log(`Produk: ${this.nama}, Harga: ${this.harga}`);
  }
}
```

## 🔹 Instantiate (Instansiasi)

Instansiasi adalah proses membuat objek dari class menggunakan `new`.

```js
const produkBaru = new Produk("Sepatu", 250000);
produkBaru.info(); // Produk: Sepatu, Harga: 250000
```

## 🔹 `toFixed()`

Digunakan untuk membulatkan angka desimal ke jumlah digit tertentu. Menghasilkan string.

```js
const harga = 19.456;
console.log(harga.toFixed(2)); // "19.46"
```

Konversi ke number jika perlu:

```js
const hargaFix = parseFloat(harga.toFixed(2));
```

## 🔹 `confirm()`

Menampilkan dialog konfirmasi (OK/Cancel). Hasilnya `true` atau `false`.

```js
const yakin = confirm("Apakah kamu yakin?");
if (yakin) {
  console.log("Kamu memilih YA");
} else {
  console.log("Kamu memilih TIDAK");
}
```

## 🔹 `bind()`

`bind()` digunakan untuk mengunci konteks `this` pada sebuah fungsi agar tetap mengarah ke objek tertentu.

```js
const user = {
  nama: "Dina",
  sapa() {
    console.log(`Halo, saya ${this.nama}`);
  },
};

const tombol = document.querySelector("button");
tombol.addEventListener("click", user.sapa.bind(user));
```

## 💡 Tips

- Pakai `toFixed()` untuk format angka seperti harga atau persen.
- Gunakan `bind()` jika `this` berubah di dalam callback atau event handler.
- Jangan lupa `this` dalam class merujuk ke objek yang dibuat dengan `new`.

---
