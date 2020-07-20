#/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package tiket;

/**
 *
 * @author Acer
 */
import java.util.Scanner;
public class tiketbiasa {
    int kelas,penumpang,total;
    
    public void setKelas(int kelas) {
    this.kelas = kelas;
    }
    
    public int getKelas(){
    return kelas;
    }
    
    public void setPenumpang(int penumpang){
    this.penumpang = penumpang;
    }
    
    public int getPenumpang(){
    return penumpang;
    }
    
    public void setTotal(int total){
    this.total = total;
    }
    
    public int getTotal(){
    return total;
    }
    
    public void infobeli(){
        switch (kelas){
            case 1:
                System.out.println("Ekonomi = Rp.15000");
                setTotal(15000*penumpang);
                System.out.println("Harga Tiket = Rp.15000");
                System.out.println("Total Harga = Rp."+getTotal());
                break;
            case 2:
                System.out.println("Bisnis = Rp.80000");
                setTotal(80000*penumpang);
                System.out.println("Harga Tiket = Rp.80000");
                System.out.println("Total Harga = Rp."+getTotal());
                break;
            case 3:
                System.out.println("Ekonomi = Rp.110000");
                setTotal(110000*penumpang);
                System.out.println("Harga Tiket = Rp.110000");
                System.out.println("Total Harga = Rp."+getTotal());
                break;
            default:
                System.out.println("Maaf Pilihan yang Anda Pilih Tidak Tersedia. Silahkan Coba Lagi");
                System.out.println("\n");
                tiketbiasa set = new tiketbiasa();
                set.menu();
                set.infobeli();
                break;
        }       
    }
    
    public void menu(){
        Scanner scan = new Scanner(System.in);
        System.out.println("-----KERETA API MAYAT-----");
        System.out.println("     Surabaya-Malang    ");
        System.out.print("\n");
        System.out.println("1.Ekonomi     Rp.15.000");
        System.out.println("2.Bisnis      Rp.80.000");
        System.out.println("3.Eksekutif   Rp.110.000");
        do {
            System.out.print("Masukkan pilihan Tiket Anda : ");
            while (!scan.hasNextInt()) {
                System.out.println("Masukkan hanya Angka !");
                scan.next();
                System.out.print("Masukkan pilihan Tiket Anda : ");
            }
            kelas = scan.nextInt();
            do {
                System.out.print("Masukkan Jumlah Tiket : ");
                while (!scan.hasNextInt()) {
                    System.out.println("Masukkan hanya Angka !");
                    scan.next();
                    System.out.println("Masukkan Jumlah Tiket : ");
                }
                penumpang = scan.nextInt();
            } while (penumpang <= 0);
        } while (penumpang <= 0);
    }
    
    public static void main(String[] args) {
        tiketbiasa set = new tiketbiasa();
        set.menu();
        set.infobeli();
    }
}
