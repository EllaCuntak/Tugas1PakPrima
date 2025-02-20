import java.util.Scanner;  // Mengimpor kelas Scanner yang digunakan untuk membaca input dari pengguna

public class tim5uas {  // Mendeklarasikan nama kelas yaitu "tim5uas"
    public static void main(String[] args) {  // Metode utama untuk menjalankan program
        Scanner input = new Scanner(System.in);  // Membuat objek input untuk membaca input dari pengguna
        int menu;  // Variabel untuk menyimpan pilihan menu yang dipilih pengguna
        int maxData = 100;  // Membatasi jumlah data maksimal yang bisa disimpan (100 data)
        int index = 0;  // Variabel untuk melacak jumlah data yang sudah dimasukkan
        // Mendeklarasikan array untuk menyimpan data mahasiswa
        String[] namaMahasiswa = new String[maxData]; // Mendeklarasikan array namaMahasiswa untuk menyimpan nama-nama mahasiswa. Ukurannya dibatasi oleh maxData (100).
        String[] jenisPrestasi = new String[maxData]; // Mendeklarasikan array jenisPrestasi untuk menyimpan jenis prestasi yang diraih mahasiswa.
        String[] tingkatPrestasi = new String[maxData]; // Mendeklarasikan array tingkatPrestasi untuk menyimpan tingkat prestasi mahasiswa (misalnya, lokal, nasional, internasional).
        long[] nimMahasiswa = new long[maxData];
        int[] tahunPrestasi = new int[maxData];

        do {  // Memulai sebuah loop yang akan terus berulang sampai pengguna memilih untuk keluar
            // Menampilkan menu utama untuk pengguna memilih tindakan yang ingin dilakukan
            System.out.println("======= PENCATATAN PRESTASI MAHASISWA =======");
            System.out.println("1. Tambah Data Prestasi");
            System.out.println("2. Tampilkan Semua Prestasi");
            System.out.println("3. Analisis Prestasi Berdasarkan Nama");
            System.out.println("4. Analisis Prestasi Berdasarkan Jenis");
            System.out.println("5. Analisis Prestasi Berdasarkan Tingkat");
            System.out.println("6. Analisis Prestasi Berdasarkan Tahun");
            System.out.println("7. Keluar");
            System.out.print("Pilih menu: ");
            menu = input.nextInt();  // Membaca input angka menu yang dipilih
            input.nextLine();  // Membersihkan input buffer setelah membaca input angka
            if (menu == 1) {  // Jika pengguna memilih menu untuk menambah data prestasi
                System.out.print("Masukan Nama Mahasiswa: ");
                namaMahasiswa[index] = input.nextLine();  // Meminta dan menyimpan nama mahasiswa
                System.out.print("Masukan NIM Mahasiswa: ");
                nimMahasiswa[index] = input.nextLong();  // Meminta dan menyimpan NIM mahasiswa
                input.nextLine();  // Membersihkan input buffer setelah membaca NIM

                do {  // Meminta jenis prestasi dengan validasi, agar input hanya "juara 1", "juara 2", atau "juara 3"
                    System.out.print("Masukan Jenis Prestasi (juara 1-3): ");
                    jenisPrestasi[index] = input.nextLine();  // Membaca input jenis prestasi
                    // Memeriksa apakah jenis prestasi yang dimasukkan valid
                    if (jenisPrestasi[index].equalsIgnoreCase("juara 1")) {
                        break;  // Jika valid, keluar dari loop
                    } else if (jenisPrestasi[index].equalsIgnoreCase("juara 2")) {
                        break;  // Jika valid, keluar dari loop
                    } else if (jenisPrestasi[index].equalsIgnoreCase("juara 3")) {
                        break;  // Jika valid, keluar dari loop
                    } else {
                        System.out.println("Jenis prestasi tidak valid. Coba lagi");  // Jika input tidak valid, beri pesan error
                    }
                } while (true);  // Loop terus berjalan sampai input valid

                do {  // Meminta tingkat prestasi dengan validasi, agar input hanya "lokal", "nasional", atau "internasional"
                    System.out.print("Masukan Tingkat Prestasi (Lokal/Nasional/Internasional): ");
                    tingkatPrestasi[index] = input.nextLine();  // Membaca input tingkat prestasi
                    // Memeriksa apakah tingkat prestasi yang dimasukkan valid
                    if (tingkatPrestasi[index].equalsIgnoreCase("lokal")) {
                        break;  // Jika valid, keluar dari loop
                    } else if (tingkatPrestasi[index].equalsIgnoreCase("nasional")) {
                        break;  // Jika valid, keluar dari loop
                    } else if (tingkatPrestasi[index].equalsIgnoreCase("internasional")) {
                        break;  // Jika valid, keluar dari loop
                    } else {
                        System.out.println("Tingkat prestasi tidak valid. Coba lagi");  // Jika input tidak valid, beri pesan error
                    }
                } while (true);

                do {  // Meminta tahun prestasi dengan validasi, agar tahun berada dalam rentang 2010-2024
                    System.out.print("Masukan Tahun Prestasi (2010-2024): ");
                    tahunPrestasi[index] = input.nextInt();  // Membaca input tahun prestasi
                    // Memeriksa apakah tahun prestasi yang dimasukkan valid
                    if (tahunPrestasi[index] >= 2010 && tahunPrestasi[index] <= 2024) {
                        break;  // Jika valid, keluar dari loop
                    } else {
                        System.out.println("Tahun prestasi tidak valid. Coba lagi");  // Jika input tidak valid, beri pesan error
                    }
                } while (true);

                System.out.println("Data prestasi berhasil ditambahkan");  // Menampilkan pesan bahwa data telah berhasil ditambahkan
                System.out.println();
                index++;  // Menambah nilai index untuk menyimpan data berikutnya
            } else if (menu == 2) {  // Jika pengguna memilih menu untuk menampilkan semua data prestasi
                if (index == 0) {  // Memeriksa apakah belum ada data yang dimasukkan
                    System.out.println("Belum ada data prestasi");
                    System.out.println();
                } else {
                    System.out.println("=========== DAFTAR SEMUA PRESTASI ===========");
                    // Menampilkan semua data prestasi yang telah dimasukkan
                    for (int i = 0; i < index; i++) {
                        System.out.println("Nama: " + namaMahasiswa[i] + " | NIM: " + nimMahasiswa[i] +
                                " | Jenis: " + jenisPrestasi[i] + " | Tingkat: " + tingkatPrestasi[i] +
                                " | Tahun: " + tahunPrestasi[i]);
                    }
                    System.out.println();
                }
            } else if (menu == 3) {  // Jika pengguna memilih menu untuk menganalisis prestasi berdasarkan nama
                if (index == 0) {  // Memeriksa apakah belum ada data yang dimasukkan
                    System.out.println("Belum ada data prestasi");
                    System.out.println();
                } else {
                    System.out.print("Masukan Nama Prestasi Yang Ingin Di Analisis: ");
                    String cek = input.nextLine();  // Mengambil nama yang ingin dianalisis
                    System.out.println();
                    System.out.println("============= ANALISIS PRESTASI =============");
                    // Menampilkan data prestasi yang nama mahasiswa-nya sesuai dengan input
                    for (int i = 0; i < index; i++) {
                        if (cek.equalsIgnoreCase(namaMahasiswa[i])) {  // Membandingkan nama yang dimasukkan dengan data
                            System.out.println("Nama: " + namaMahasiswa[i] + " | NIM: " + nimMahasiswa[i] +
                                    " | Jenis: " + jenisPrestasi[i] + " | Tingkat: " + tingkatPrestasi[i] +
                                    " | Tahun: " + tahunPrestasi[i]);
                        }
                    }
                    System.out.println();
                }
            } else if (menu == 4) {  // Jika pengguna memilih menu untuk menganalisis prestasi berdasarkan jenis
                if (index == 0) {  // Memeriksa apakah belum ada data yang dimasukkan
                    System.out.println("Belum ada data prestasi");
                    System.out.println();
                } else {
                    System.out.print("Masukan Jenis Prestasi Yang Ingin Di Analisis: ");
                    String cek = input.nextLine();  // Mengambil jenis prestasi yang ingin dianalisis
                    System.out.println();
                    System.out.println("============= ANALISIS PRESTASI =============");
                    // Menampilkan data prestasi yang jenis prestasi-nya sesuai dengan input
                    for (int i = 0; i < index; i++) {
                        if (cek.equalsIgnoreCase(jenisPrestasi[i])) {  // Membandingkan jenis prestasi
                            System.out.println("Nama: " + namaMahasiswa[i] + " | NIM: " + nimMahasiswa[i] +
                                    " | Jenis: " + jenisPrestasi[i] + " | Tingkat: " + tingkatPrestasi[i] +
                                    " | Tahun: " + tahunPrestasi[i]);
                        }
                    }
                    System.out.println();
                }
            } else if (menu == 5) {  // Jika pengguna memilih menu untuk menganalisis prestasi berdasarkan tingkat
                if (index == 0) {  // Memeriksa apakah belum ada data yang dimasukkan
                    System.out.println("Belum ada data prestasi");
                    System.out.println();
                } else {
                    System.out.print("Masukan Tingkat Prestasi Yang Ingin Di Analisis: ");
                    String cek = input.nextLine();  // Mengambil tingkat prestasi yang ingin dianalisis
                    System.out.println();
                    System.out.println("============= ANALISIS PRESTASI =============");
                    // Menampilkan data prestasi yang tingkat prestasi-nya sesuai dengan input
                    for (int i = 0; i < index; i++) {
                        if (cek.equalsIgnoreCase(tingkatPrestasi[i])) {  // Membandingkan tingkat prestasi
                            System.out.println("Nama: " + namaMahasiswa[i] + " | NIM: " + nimMahasiswa[i] +
                                    " | Jenis: " + jenisPrestasi[i] + " | Tingkat: " + tingkatPrestasi[i] +
                                    " | Tahun: " + tahunPrestasi[i]);
                        }
                    }
                    System.out.println();
                }
            } else if (menu == 6) {  // Jika pengguna memilih menu untuk menganalisis prestasi berdasarkan tahun
                if (index == 0) {  // Memeriksa apakah belum ada data yang dimasukkan
                    System.out.println("Belum ada data prestasi");
                    System.out.println();
                } else {
                    System.out.print("Masukan Tahun Prestasi Yang Ingin Di Analisis: ");
                    int cek = input.nextInt();  // Mengambil tahun prestasi yang ingin dianalisis
                    System.out.println();
                    System.out.println("============= ANALISIS PRESTASI =============");
                    // Menampilkan data prestasi yang tahun-nya sesuai dengan input
                    for (int i = 0; i < index; i++) {
                        if (cek == tahunPrestasi[i]) {  // Membandingkan tahun prestasi
                            System.out.println("Nama: " + namaMahasiswa[i] + " | NIM: " + nimMahasiswa[i] +
                                    " | Jenis: " + jenisPrestasi[i] + " | Tingkat: " + tingkatPrestasi[i] +
                                    " | Tahun: " + tahunPrestasi[i]);
                        }
                    }
                    System.out.println();
                }
            } else if (menu == 7) {  // Jika pengguna memilih menu untuk keluar dari program
                break;  // Menghentikan loop dan keluar dari program
            }

        } while (true);  // Loop terus berjalan sampai pengguna memilih menu keluar
    }
}
