---
title: Menambahkan Bidang Formulir dalam Dokumen PDF menggunakan Java
linktitle: Menambahkan Bidang Formulir dalam Dokumen PDF menggunakan Java
second_title: API Pemrosesan PDF Java Aspose.PDF
description: Pelajari cara menambahkan kolom formulir interaktif ke dokumen PDF Anda menggunakan Java dan Aspose.PDF untuk Java. Buat formulir PDF yang mudah digunakan dengan mudah.
type: docs
weight: 10
url: /id/java/pdf-form-fields/add-form-field-in-pdf-document-using-java/
---

## Perkenalan

Menambahkan kolom formulir ke dokumen PDF akan meningkatkan fungsinya dengan memungkinkan pengguna memasukkan data langsung ke dalam dokumen. Ini dapat sangat berguna untuk berbagai keperluan, seperti membuat formulir yang dapat diisi, survei, atau laporan dengan konten yang dibuat pengguna.

Kami akan menggunakan Aspose.PDF untuk Java, pustaka canggih yang menyederhanakan manipulasi PDF dalam aplikasi Java. Dengan Aspose.PDF, Anda dapat dengan mudah membuat, memodifikasi, dan memanipulasi dokumen PDF, termasuk menambahkan kolom formulir secara dinamis.

## Menyiapkan Lingkungan

Sebelum kita mulai membuat kode, Anda perlu menyiapkan lingkungan pengembangan. Ikuti langkah-langkah berikut:

1.  Unduh Aspose.PDF untuk Java: Kunjungi situs web Aspose dan unduh versi terbaru Aspose.PDF untuk Java. Anda dapat menemukannya[Di Sini](https://releases.aspose.com/pdf/java/).

2. Instal Aspose.PDF: Setelah mengunduh, instal Aspose.PDF dengan mengikuti petunjuk instalasi yang disediakan di situs web.

3. Buat Proyek Java: Buat proyek Java baru di Lingkungan Pengembangan Terpadu (IDE) pilihan Anda dan sertakan pustaka Aspose.PDF dalam proyek Anda.

## Membuat Dokumen PDF Baru

Mari kita mulai dengan membuat dokumen PDF baru. Dalam contoh ini, kita akan membuat file PDF sederhana dengan judul dan beberapa petunjuk.

```java
// Impor pustaka Aspose.PDF
import com.aspose.pdf.*;

public class AddFormFieldPDF {
    public static void main(String[] args) {
        // Buat dokumen PDF baru
        Document doc = new Document();

        // Tambahkan halaman ke dokumen
        Page page = doc.getPages().add();

        // Tambahkan judul
        TextFragment title = new TextFragment("Feedback Form");
        title.getTextState().setFontSize(18);
        title.getTextState().setFont(FontRepository.findFont("Arial"));
        page.getParagraphs().add(title);

        // Tambahkan instruksi
        TextFragment instructions = new TextFragment("Please provide your feedback below:");
        instructions.getTextState().setFontSize(12);
        page.getParagraphs().add(instructions);

        // Simpan dokumen ke file
        doc.save("FeedbackForm.pdf");
    }
}
```

Dalam cuplikan kode ini, kami membuat dokumen PDF baru, menambahkan halaman, dan menyisipkan judul dan beberapa instruksi.

## Menambahkan Bidang Formulir

Sekarang, mari kita lanjutkan dengan menambahkan kolom formulir ke dokumen PDF kita. Kita akan menyertakan kolom teks, kotak centang, dan tombol radio untuk membuat formulir umpan balik yang interaktif.

### Bidang Teks

Kolom teks memungkinkan pengguna memasukkan teks. Berikut cara menambahkan kolom teks:

```java
// Buat bidang teks
TextField textField = new TextField(page, new Rectangle(100, 300, 200, 20));
textField.getPdfObject().setBorderStyle(new BorderStyle(1)); // Mengatur gaya batas
textField.setPartialName("txtName"); // Tetapkan nama bidang
textField.setMultiline(false); // Nonaktifkan multiline
page.getAnnotations().add(textField);
```

### Kotak centang

Kotak centang digunakan untuk opsi biner (misalnya, pertanyaan ya/tidak). Berikut cara menambahkan kotak centang:

```java
// Buat kotak centang
CheckboxField checkboxField = new CheckboxField(page, new Rectangle(100, 250, 20, 20));
checkboxField.setPartialName("chkAgree"); // Tetapkan nama bidang
checkboxField.setChecked(false); // Awalnya tidak dicentang
page.getAnnotations().add(checkboxField);
```

### Tombol Radio

Tombol radio digunakan saat pengguna perlu memilih satu opsi dari suatu grup. Setiap opsi merupakan tombol radio yang terpisah, tetapi semuanya termasuk dalam grup yang sama. Berikut cara menambahkan tombol radio:

```java
// Buat tombol radio
RadioButtonOptionField option1 = new RadioButtonOptionField(page, new Rectangle(100, 200, 20, 20));
RadioButtonOptionField option2 = new RadioButtonOptionField(page, new Rectangle(100, 180, 20, 20));
option1.setPartialName("optYes"); // Tetapkan nama bidang untuk opsi 1
option2.setPartialName("optNo"); // Tetapkan nama bidang untuk opsi 2

//Tambahkan opsi ke grup tombol radio
RadioButtonOptionField[] options = {option1, option2};
RadioButtonField radioButtonField = new RadioButtonField(page, options);
page.getAnnotations().add(radioButtonField);
```

Dengan contoh kode ini, Anda dapat menambahkan kolom teks, kotak centang, dan tombol radio ke dokumen PDF Anda. Pastikan untuk menyesuaikan propertinya sesuai kebutuhan, seperti nama kolom dan nilai default.

## Menyesuaikan Bidang Formulir

Menyesuaikan kolom formulir memungkinkan Anda mengontrol tampilan dan perilakunya. Anda dapat mengubah properti seperti ukuran font, warna teks, gaya border, dan banyak lagi.

### Mengubah Properti Bidang

Katakanlah Anda ingin mengubah ukuran font dan warna teks pada kolom teks:

```java
textField.getTextState().setFontSize(14);
textField.getTextState().setForegroundColor(Color.getGreen());
```

### Validasi Lapangan

Anda juga dapat menetapkan aturan validasi untuk kolom formulir. Misalnya, Anda dapat meminta pengguna untuk memasukkan alamat email yang valid di kolom teks:

```java
textField.getValidation().add(ValidationType.EMAIL);
```

## Menetapkan Nilai Bidang

Untuk mengisi kolom formulir dengan data, Anda dapat mengatur nilai default secara terprogram. Ini berguna untuk membuat templat atau mengisi informasi yang diketahui sebelumnya.

```java
textField.setValue("John Doe"); // Tetapkan nilai default untuk bidang teks
checkboxField.setChecked(true); // Centang kotak centang secara default
```

## Pengiriman dan Validasi Formulir

Menambahkan kolom formulir hanya setengah dari cerita; Anda juga ingin

 untuk mengaktifkan pengiriman dan validasi formulir.

### Pengiriman Formulir

Untuk mengizinkan pengguna mengirimkan data formulir, Anda perlu menentukan tindakan, seperti mengirim email atau mengirimkan ke server web. Berikut ini contoh cara menyiapkan tombol kirim:

```java
ButtonField submitButton = new ButtonField(page, new Rectangle(100, 50, 80, 30));
submitButton.getPdfObject().setBorderStyle(new BorderStyle(1));
submitButton.getActions().getOnPushButton().add(new SubmitFormAction("https://serveranda.com/submit", SubmitFormActionType.URL, "FeedbackForm.pdf"));
page.getAnnotations().add(submitButton);
```

### Validasi Formulir

Validasi memastikan bahwa masukan pengguna memenuhi kriteria tertentu. Misalnya, Anda dapat memvalidasi kolom nomor telepon agar hanya menerima angka:

```java
textField.getValidation().add(ValidationType.NUMBER);
```

## Menyimpan dan Mengekspor

Setelah Anda membuat dan menyesuaikan dokumen PDF dengan kolom formulir, saatnya menyimpan atau mengekspornya. Aspose.PDF menyediakan berbagai opsi untuk ini.

### Simpan ke File Lokal

Untuk menyimpan dokumen PDF ke berkas lokal, gunakan kode berikut:

```java
doc.save("FeedbackForm.pdf");
```

### Simpan ke Aliran

 Untuk menyimpan dokumen PDF ke aliran, Anda dapat menggunakan`OutputStream` kelas:

```java
OutputStream outputStream = new FileOutputStream("FeedbackForm.pdf");
doc.save(outputStream);
outputStream.close();
```

## Kesimpulan

Dalam panduan lengkap ini, kami telah mempelajari cara menambahkan kolom formulir ke dokumen PDF menggunakan Java dan Aspose.PDF untuk Java. Anda telah mempelajari cara membuat kolom teks, kotak centang, dan tombol radio, menyesuaikan propertinya, menetapkan nilai default, mengaktifkan pengiriman dan validasi formulir, serta menyimpan/mengekspor dokumen PDF.

## Tanya Jawab Umum

### Bagaimana cara mengatur daftar dropdown dalam formulir PDF?

 Untuk membuat daftar dropdown (kotak kombo) dalam formulir PDF, Anda dapat menggunakan`ComboBoxField` kelas yang disediakan oleh Aspose.PDF untuk Java. Ikuti pendekatan serupa seperti yang ditunjukkan untuk bidang formulir lainnya, dan sesuaikan opsi menggunakan`AddItem` metode. Anda dapat menemukan dokumentasi terperinci tentang ini di situs web Aspose.

### Apakah Aspose.PDF untuk Java kompatibel dengan pustaka dan kerangka kerja Java lainnya?

Ya, Aspose.PDF untuk Java kompatibel dengan berbagai pustaka dan kerangka kerja Java. Anda dapat mengintegrasikannya ke dalam aplikasi Java Anda, baik Anda menggunakan Spring, JavaFX, atau kerangka kerja populer lainnya. Pastikan untuk memeriksa dokumentasi dan sumber daya untuk panduan integrasi tertentu.

### Bisakah saya melindungi kata sandi formulir PDF yang dibuat dengan Aspose.PDF untuk Java?

Tentu saja! Aspose.PDF untuk Java memungkinkan Anda menambahkan perlindungan kata sandi ke dokumen PDF Anda, termasuk formulir. Anda dapat mengatur kata sandi tingkat pengguna dan tingkat pemilik untuk membatasi akses dan izin. Lihat dokumentasi untuk petunjuk terperinci tentang cara menerapkan fitur keamanan ini.

### Bagaimana cara mengekstrak data yang dikirimkan melalui formulir PDF?

Untuk mengekstrak data yang dikirimkan melalui formulir PDF, Anda perlu menangani pengiriman formulir di server atau aplikasi backend Anda. Saat pengguna mengirimkan formulir, Anda dapat menerima data dan memprosesnya sesuai kebutuhan. Aspose.PDF menyediakan alat untuk mengekstrak data formulir secara terprogram dari dokumen PDF di sisi server.

### Bisakah saya membuat formulir PDF secara dinamis berdasarkan masukan pengguna?

Ya, Anda dapat membuat formulir PDF secara dinamis berdasarkan masukan pengguna menggunakan Aspose.PDF untuk Java. Bergantung pada masukan pengguna atau logika aplikasi, Anda dapat membuat dokumen PDF dengan berbagai bidang dan tata letak formulir. Fleksibilitas ini memungkinkan pembuatan formulir khusus yang disesuaikan dengan kebutuhan atau skenario pengguna tertentu.