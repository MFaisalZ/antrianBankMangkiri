import java.util.Scanner;

public class antrianBankMangkiri {
    private static final int MAX_SIZE = 10; // Maksimal jumlah antrian per jalur
    private static String[] queue1 = new String[MAX_SIZE]; // Antrian jalur 1
    private static String[] queue2 = new String[MAX_SIZE]; // Antrian jalur 2
    private static int front1 = -1, rear1 = -1; // Front dan rear untuk jalur 1
    private static int front2 = -1, rear2 = -1; // Front dan rear untuk jalur 2

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int choice; //variabel untuk oilih menu
        do {
            System.out.println("\n");
            System.out.println("Menu : ");
            System.out.println("1. Tambah Data Antrian");
            System.out.println("2. Hapus Antrian Elemen Pertama");
            System.out.println("3. Hapus Antrian di Posisi Tertentu");
            System.out.println("4. Hapus Semua Elemen");
            System.out.println("5. Tampilkan Data");
            System.out.println("0. Keluar");
            System.out.print("Pilih menu : ");
            choice = input.nextInt();
            switch (choice) {
                case 1:
                    enqueueTambah(input);
                    break;
                case 2:
                    dequeueAmbil();
                    break;
                case 3:
                    delete(input);
                    break;
                case 4:
                    clear();
                    break;
                case 5:
                    displayTampil();
                    break;
                case 0:
                    System.out.println("Terima kasih!. Sampai jumpa kembali");
                    break;
                default:
                    System.out.println("Pilihan tidak valid!");
            }
            System.out.println();
        } while (choice != 0);
    }
    //fungsi tambah data
    private static void enqueueTambah(Scanner input) {
        System.out.print("Masukkan data antrian : ");
        String data = input.next();
        System.out.print("Masukkan nomor jalur ke 1 atau 2 : ");
        int jalur = input.nextInt();
        switch (jalur) {
            case 1:
                if (rear1 == MAX_SIZE - 1) {
                    System.out.println("Antrian jalur 1 penuh!");
                } else {
                    if (front1 == -1) {
                        front1 = 0;
                    }
                    rear1++;
                    queue1[rear1] = data;
                    System.out.println("Data " + data + " telah ditambahkan ke antrian jalur 1");
                }   break;
            case 2:
                if (rear2 == MAX_SIZE - 1) {
                    System.out.println("Antrian jalur 2 penuh!");
                } else {
                    if (front2 == -1) {
                        front2 = 0;
                    }
                    rear2++;
                    queue2[rear2] = data;
                    System.out.println("Data " + data + " telah ditambahkan ke antrian jalur 2");
                }   break;
            default:
                System.out.println("Jalur tidak valid!");
                break;
        }
    }
    //fungsi mengambil data
    private static void dequeueAmbil() {
        if (front1 == -1 && front2 == -1) {
            System.out.println("Antrian kosong!");
        } else {
            String data;
            if (front1 != -1) {
                data = queue1[front1];
            if (front1 == rear1) {
                front1 = -1;
                rear1 = -1;
            } else {
                front1++;
            }
            System.out.println("Data " + data + " telah dihapus dari antrian jalur 1");
        } else {
            data = queue2[front2];
            if (front2 == rear2) {
                front2 = -1;
                rear2 = -1;
            } else {
                front2++;
            }
            System.out.println("Data " + data + " telah dihapus dari antrian jalur 2");
            }
        }
    }
    ///Fungsi delete
    private static void delete(Scanner input) {
        System.out.print("Masukkan nomor jalur (1 atau 2): ");
        int jalur = input.nextInt();
        System.out.print("Masukkan posisi data yang akan dihapus: ");
        int pos = input.nextInt() - 1;
            switch (jalur) {
                case 1:
                    if (front1 == -1) {
                        System.out.println("Antrian jalur 1 kosong!");
                    } else if (pos < front1 || pos > rear1) {
                        System.out.println("Posisi tidak valid!");
                    } else {
                        String data = queue1[pos];
                        for (int i = pos; i < rear1; i++) {
                            queue1[i] = queue1[i + 1];
                        }
                        queue1[rear1] = null;
                        rear1--;
                        System.out.println("Data " + data + " telah dihapus dari antrian jalur 1");
                    }       break;
                case 2:
                    if (front2 == -1) {
                        System.out.println("Antrian jalur 2 kosong!");
                    } else if (pos < front2 || pos > rear2) {
                        System.out.println("Posisi tidak valid!");
                    } else {
                        String data = queue2[pos];
                        for (int i = pos; i < rear2; i++) {
                            queue2[i] = queue2[i + 1];
                        }
                        queue2[rear2] = null;
                        rear2--;
                        System.out.println("Data " + data + " telah dihapus dari antrian jalur 2");
                    }       break;
                default:
                    System.out.println("Jalur tidak valid!");
                    break;
            }
    }
    //fungsi clear
    private static void clear() {
        if (front1 == -1 && front2 == -1) {
            System.out.println("Antrian kosong!");
        }else{
            for (int i = front1; i <= rear1; i++) {
            queue1[i] = null;
        }
            for (int i = front2; i <= rear2; i++) {
            queue2[i] = null;
        }
            front1 = -1;
            rear1 = -1;
            front2 = -1;
            rear2 = -1;
            System.out.println("Semua elemen telah dihapus dari antrian!");
        }
    }
    //fungsi menampilkan data
    private static void displayTampil() {
        if (front1 == -1 && front2 == -1) {
            System.out.println("Antrian kosong!");
        } else {
            System.out.println("Isi antrian jalur 1:");
            if (front1 == -1) {
                System.out.println("Kosong");
            } else {
                for (int i = front1; i <= rear1; i++) {
                    System.out.println((i + 1) + ". " + queue1[i]);
                }
            }
            System.out.println("Isi antrian jalur 2:");
            if (front2 == -1) {
                System.out.println("Kosong");
            } else {
                for (int i = front2; i <= rear2; i++) {
                    System.out.println((i + 1) + ". " + queue2[i]);
                }
            }
        }
    }
}
