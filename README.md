1. Import Library Scanner
import java.util.Scanner;
- Mengimpor Scanner dari java.util untuk menerima input dari pengguna.
2. Deklarasi Kelas dan Fungsi main
public class soalUAS {
    public static void main(String[] args) {
public class soalUAS → Mendeklarasikan kelas dengan nama soalUAS.
public static void main(String[] args) → Metode utama tempat eksekusi program dimulai.
3. Membuat Scanner untuk Input Pengguna
Scanner input = new Scanner(System.in);
- Membuat objek Scanner untuk membaca input dari keyboard.
4. Deklarasi Array Menu dan Harga
String[] menu = {"Nasi Goreng", "Mie Goreng", "Roti Bakar", "Kentang Goreng", 
                 "Teh Tarik", "Cappucino", "Chocolate Ice"};
int[] harga = {20000, 15000, 12000, 10000, 8000, 20000, 25000};
- menu → Array yang berisi daftar makanan/minuman.
- harga → Array yang berisi harga setiap menu sesuai dengan indeksnya.
5. Deklarasi Array untuk Menyimpan Jumlah Pesanan
int[] jumlahPesanan = new int[menu.length];
jumlahPesanan → Array untuk menyimpan jumlah pesanan setiap menu.
menu.length → Panjang array menu, memastikan ukuran array sesuai jumlah menu.
6. Variabel untuk Menyimpan Pilihan Menu
int pilihan;
pilihan → Menyimpan input dari pengguna (menu utama yang dipilih).
7. Menampilkan Selamat Datang
System.out.println("=== Selamat Datang di Kafe ===");
- Menampilkan pesan sambutan saat program dimulai.
8. Memulai Perulangan do-while
do { 
- Menggunakan do-while agar program tetap berjalan hingga pengguna memilih "Selesai".
9. Menampilkan Menu Utama
System.out.println("\nPilih Menu Utama berikut:");
System.out.println("1. Tambah Pesanan"); 
System.out.println("2. Lihat Daftar Pesanan");
System.out.println("3. Hitung Total Biaya");
System.out.println("4. Selesai");
- Menampilkan pilihan utama untuk pengguna.
10. Meminta Input Pilihan Pengguna
System.out.print("Masukkan pilihan Anda: ");
pilihan = input.nextInt();
- Meminta input dari pengguna dan menyimpannya di variabel pilihan.
Switch-Case: Mengelola Pilihan Pengguna
- Kode berikut menangani setiap pilihan yang dimasukkan pengguna.
11. Pilihan 1: Tambah Pesanan
case 1:
- Jika pengguna memilih 1, maka program menampilkan daftar menu.
System.out.println("\n=== DAFTAR MENU ===");
for (int i = 0; i < menu.length; i++) {
    System.out.println((i + 1) + ". " + menu[i] + " - Rp" + harga[i]);
}
- Menampilkan semua menu dan harga.
System.out.print("Masukkan nomor menu yang ingin dipesan: ");
int nomorMenu = input.nextInt();
- Meminta pengguna memasukkan nomor menu yang ingin dipesan.
if (nomorMenu < 1 || nomorMenu > menu.length) {
    System.out.println("Menu tidak valid!");
} else {
    System.out.print("Masukkan jumlah pesanan: ");
    int jumlah = input.nextInt();
    System.out.println(" ");
    jumlahPesanan[nomorMenu - 1] += jumlah;
    System.out.println(jumlah + " " + menu[nomorMenu - 1] + " berhasil ditambahkan ke pesanan.");
}
- Validasi input untuk memastikan menu yang dipilih benar.
- Menambahkan jumlah pesanan ke dalam array jumlahPesanan.
12. Pilihan 2: Melihat Daftar Pesanan
case 2:
System.out.println("\n=== Daftar Pesanan ===");
boolean Pesanan = false;
- Menampilkan daftar pesanan yang sudah dimasukkan pengguna.
for (int i = 0; i < menu.length; i++) {
    if (jumlahPesanan[i] > 0) {
        System.out.println(menu[i] + " x " + jumlahPesanan[i]);
        Pesanan = true;
    }
}
if (!Pesanan) {
    javaSystem.out.println("Belum ada pesanan.");
}
- Jika ada pesanan, akan ditampilkan.
- Jika tidak ada pesanan, muncul pesan "Belum ada pesanan."
13. Pilihan 3: Menghitung Total Biaya
case 3:
int totalBiaya = 0;
System.out.println("\n=== Total Biaya ===");
- Menginisialisasi totalBiaya untuk menyimpan total harga pesanan.
for (int i = 0; i < menu.length; i++) {
    if (jumlahPesanan[i] > 0) {
        int biaya = jumlahPesanan[i] * harga[i];
        System.out.println(menu[i] + " x " + jumlahPesanan[i] + " = Rp" + biaya);
        totalBiaya += biaya;
    }
}
System.out.println("Total Biaya: Rp" + totalBiaya);
- Menghitung dan menampilkan total biaya pesanan.
14. Pilihan 4: Keluar dari Program
case 4:
System.out.println("\nTerima kasih! Selamat tinggal.");
System.out.println(" ");
break;
- Menampilkan pesan "Terima kasih! Selamat tinggal."
- Mengakhiri program.
15. Default: Input Tidak Valid
default:
System.out.println("Pilihan tidak valid. Silakan coba lagi.");
- Jika input tidak valid, program meminta pengguna untuk memilih kembali.
16. Perulangan Berjalan Hingga Pilihan 4
} while(pilihan != 4);
- Loop do-while berjalan terus hingga pengguna memilih 4 (Selesai).
17. Menutup Scanner
input.close();
- Menutup objek Scanner untuk menghindari kebocoran sumber daya.