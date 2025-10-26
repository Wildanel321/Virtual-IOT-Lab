# ⚡ Virtual IoT Lab - ESP32 Simulator

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

**Virtual IoT Lab** adalah simulator IoT interaktif berbasis web yang memungkinkan Anda belajar konsep ESP32, sensor, dan pemrograman mikrokontroler secara visual tanpa perangkat fisik.

![Virtual IoT Lab Preview](https://via.placeholder.com/800x400/0a0e27/00d9ff?text=Virtual+IoT+Lab+Preview)

---

## 🌟 Fitur Utama

### 🎯 Workspace Interaktif
- **ESP32 DevKit Virtual** - Board ESP32 yang dapat dihubungkan dengan berbagai komponen
- **Drag & Drop Interface** - Seret komponen dari sidebar ke board dengan mudah
- **Visual Feedback** - Semua interaksi memiliki animasi dan efek visual futuristik

### 📦 Komponen IoT Tersedia
| Komponen | Icon | Fungsi |
|----------|------|--------|
| LED | 💡 | Lampu yang bisa dikontrol ON/OFF dengan efek glow |
| Sensor Suhu | 🌡️ | Menghasilkan data suhu 25-35°C secara real-time |
| Sensor Jarak | 📏 | Ultrasonic sensor dengan range 5-100 cm |
| RFID Reader | 💳 | Pembaca kartu RFID dengan generator ID acak |
| Servo Motor | ⚙️ | Motor servo dengan kontrol sudut 0-180° |

### 💻 Pseudo Code Editor
- Editor kode bawaan untuk menulis logika pemrograman
- Mendukung syntax pseudo-code yang mudah dipahami
- Eksekusi real-time dengan feedback visual

### 🖥️ Terminal Output
- Log aktivitas real-time
- Menampilkan status komponen
- Error handling dengan color coding

### 🎨 Desain Futuristik
- Tema cyberpunk dengan warna neon (biru & ungu)
- Background animasi grid dengan partikel interaktif
- Font modern: Orbitron & Poppins
- Efek hover glow pada semua elemen interaktif

### 💾 Persistent Storage
- Auto-save setiap 5 detik
- State tersimpan di localStorage
- Restore otomatis saat reload halaman

### 🌓 Theme Toggle
- Mode Dark (default) - Ideal untuk coding
- Mode Light - Nyaman untuk mata siang hari

---

## 🚀 Cara Menggunakan

### 1️⃣ Instalasi
```bash
# Clone atau download file HTML
# Tidak perlu instalasi, cukup buka file di browser!
```

### 2️⃣ Menambahkan Komponen
1. **Drag** komponen dari sidebar kiri
2. **Drop** ke area board ESP32
3. Komponen akan muncul dengan nilai default
4. Anda bisa **memindahkan** posisi komponen dengan drag
5. Klik tombol **×** untuk menghapus komponen

### 3️⃣ Menulis Kode Pseudo

#### Contoh 1: Kontrol LED Berdasarkan Suhu
```javascript
if (temp > 30) {
    LED.on();
} else {
    LED.off();
}
```

#### Contoh 2: Kontrol Servo Berdasarkan Jarak
```javascript
if (distance < 10) {
    servo.angle(0);
} else if (distance < 50) {
    servo.angle(90);
} else {
    servo.angle(180);
}
```

#### Contoh 3: RFID Scanner
```javascript
RFID.scan();
```

### 4️⃣ Menjalankan Simulasi
1. Tulis kode di **Pseudo Code Editor** (panel kanan)
2. Klik tombol **▶️ Run Simulation**
3. Lihat hasil di board dan terminal output

---

## 📚 Tutorial Komponen

### 💡 LED (Light Emitting Diode)
**Variabel:** Tidak ada (kontrol langsung)

**Fungsi:**
- `LED.on()` - Menyalakan LED dengan efek glow merah
- `LED.off()` - Mematikan LED

**Contoh Penggunaan:**
```javascript
// LED otomatis menyala
LED.on();

// LED otomatis mati
LED.off();

// LED berdasarkan kondisi
if (temp > 28) {
    LED.on();
}
```

---

### 🌡️ Sensor Suhu (Temperature Sensor)
**Variabel:** `temp`

**Range:** 25.0 - 35.0°C

**Contoh Penggunaan:**
```javascript
// Cek suhu dan kontrol LED
if (temp > 30) {
    LED.on();
} else {
    LED.off();
}

// Multiple conditions
if (temp < 27) {
    servo.angle(0);
} else if (temp < 32) {
    servo.angle(90);
} else {
    servo.angle(180);
}
```

---

### 📏 Sensor Jarak (Ultrasonic Distance Sensor)
**Variabel:** `distance`

**Range:** 5 - 100 cm

**Contoh Penggunaan:**
```javascript
// Deteksi objek dekat
if (distance < 20) {
    LED.on();
    servo.angle(90);
}

// Parking sensor logic
if (distance < 10) {
    LED.on();
} else {
    LED.off();
}
```

---

### 💳 RFID Reader
**Fungsi:** `RFID.scan()`

**Output:** Generates random hex ID (e.g., 0xA1B23F)

**Contoh Penggunaan:**
```javascript
// Scan RFID card
RFID.scan();

// Dalam praktik, klik tombol "Scan" pada komponen RFID di board
```

---

### ⚙️ Servo Motor
**Fungsi:** `servo.angle(degrees)`

**Range:** 0° - 180°

**Contoh Penggunaan:**
```javascript
// Set sudut spesifik
servo.angle(90);

// Sweep berdasarkan sensor
if (distance < 30) {
    servo.angle(0);
} else if (distance < 60) {
    servo.angle(90);
} else {
    servo.angle(180);
}
```

---

## 🎮 Kontrol & Shortcut

| Aksi | Cara |
|------|------|
| Tambah Komponen | Drag dari sidebar → Drop ke board |
| Pindah Komponen | Drag komponen di board |
| Hapus Komponen | Klik tombol **×** pada komponen |
| Run Kode | Klik **▶️ Run Simulation** |
| Clear Editor | Klik **🗑️ Clear** |
| Reset Lab | Klik **🔄 Reset Lab** di header |
| Tutorial | Klik **📚 Tutorial** di header |
| Toggle Theme | Klik toggle switch di header |

---

## 💡 Tips & Trik

### ✅ Best Practices
1. **Tambahkan sensor dulu** sebelum menulis kode yang menggunakannya
2. **Test kode sederhana** dulu sebelum logika kompleks
3. **Gunakan terminal** untuk melihat log aktivitas
4. **Save state otomatis** - tidak perlu khawatir kehilangan progress

### ⚡ Kombinasi Menarik
```javascript
// Smart Home Temperature Control
if (temp > 30) {
    LED.on();
    servo.angle(180);  // Buka ventilasi
} else {
    LED.off();
    servo.angle(0);    // Tutup ventilasi
}

// Parking Assistant
if (distance < 10) {
    LED.on();          // Lampu warning
    servo.angle(90);   // Stop signal
} else {
    LED.off();
    servo.angle(0);
}

// Access Control System
RFID.scan();
if (temp < 25) {
    servo.angle(90);   // Buka pintu
    LED.on();          // Indikator akses granted
}
```

---

## 🛠️ Teknologi yang Digunakan

- **HTML5** - Struktur halaman
- **CSS3** - Styling & animasi
  - Flexbox & Grid Layout
  - Backdrop Filter
  - CSS Animations
  - Custom Scrollbar
- **Vanilla JavaScript** - Logika & interaktif
  - Canvas API untuk background animation
  - Drag & Drop API
  - localStorage API
  - DOM Manipulation
- **Google Fonts** - Orbitron & Poppins

**📦 No Dependencies!** - Pure HTML, CSS, JS (No frameworks, no npm, no build tools)

---

## 📱 Responsive Design

✅ **Desktop** (1920x1080 optimal)
✅ **Laptop** (1366x768+)
✅ **Tablet** (768px+)
✅ **Mobile** (375px+)

Layout otomatis menyesuaikan:
- Grid 3 kolom (desktop) → Stack vertical (mobile)
- Scrollable workspace di mobile
- Touch-friendly drag & drop

---

## 🔧 Kustomisasi

### Mengubah Warna Tema
Edit variabel di bagian CSS:
```css
/* Primary Colors */
--neon-blue: #00d9ff;
--neon-purple: #7b2ff7;
--bg-dark: #0a0e27;
```

### Menambah Komponen Baru
1. Tambahkan item di sidebar HTML
2. Implementasikan logic di `createDroppedComponent()`
3. Tambahkan parsing di `runSimulation()`

### Mengubah Range Sensor
```javascript
// Sensor Suhu: ubah range di line ~285
const temp = (Math.random() * 10 + 25).toFixed(1); // 25-35°C
// Ubah menjadi: (Math.random() * 20 + 20) untuk 20-40°C

// Sensor Jarak: ubah range di line ~291
const dist = Math.floor(Math.random() * 95 + 5); // 5-100cm
```

---

## 🐛 Troubleshooting

### Komponen tidak bisa di-drag?
- Pastikan browser mendukung Drag & Drop API (Chrome, Firefox, Edge modern)
- Coba refresh halaman

### Kode tidak berjalan?
- Cek syntax kode pseudo (case-sensitive)
- Pastikan sensor sudah ditambahkan ke board
- Lihat terminal untuk error message

### State tidak tersimpan?
- Pastikan localStorage tidak diblokir browser
- Clear cache dan coba lagi
- Mode Incognito/Private tidak menyimpan state

### Animasi lag?
- Tutup tab browser lain
- Disable background animation jika perlu
- Gunakan browser modern (Chrome/Edge terbaru)

---

## 🎓 Use Cases

### 👨‍🎓 Pendidikan
- Pembelajaran IoT untuk pemula
- Praktikum mata kuliah embedded systems
- Workshop Arduino/ESP32 tanpa hardware

### 🏫 Sekolah/Kampus
- Demo konsep sensor dan aktuator
- Simulasi project IoT sebelum implementasi
- Latihan logika pemrograman visual

### 💼 Prototyping
- Proof of concept untuk IoT project
- Testing logic sebelum coding Arduino
- Presentasi ide ke client/team

---

## 🚧 Roadmap & Future Features

- [ ] Export kode ke Arduino IDE format
- [ ] Lebih banyak sensor (PIR, Gas, Soil Moisture)
- [ ] Multiple ESP32 boards
- [ ] Wireless communication simulation
- [ ] Save/Load project files
- [ ] Code syntax highlighting
- [ ] Step-by-step debugger
- [ ] Community sharing platform

---

## 📄 License

MIT License - Feel free to use, modify, and distribute!

---

## 👨‍💻 Author

Dibuat dengan ❤️ untuk komunitas IoT Indonesia

**Kontribusi & Feedback:**
- Buat issue untuk bug report
- Fork & pull request untuk improvement
- Share project Anda dengan hashtag #VirtualIoTLab

---

## 🙏 Acknowledgments

- Inspirasi dari TinkerCAD Circuits
- ESP32 community
- Arduino ecosystem
- Semua yang passionate tentang IoT education

---

## 📞 Support

Jika Anda menemukan bug atau punya saran:
1. Buat issue di repository
2. Atau hubungi via email/social media

---

**⭐ Jika project ini membantu, jangan lupa kasih star!**

```
 ⚡ Happy Simulating! ⚡
```

---

### 🔗 Quick Links
- [Tutorial Video](#) (Coming soon)
- [Examples Collection](#) (Coming soon)
- [Community Forum](#) (Coming soon)

---

**Last Updated:** October 2025
**Version:** 1.0.0
