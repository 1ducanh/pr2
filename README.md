/*

To change this license header, choose License Headers in Project Properties.
To change this template file, choose Tools | Templates
and open the template in the editor. */ package Exobject.java
import com.sun.javafx.font.FontResource; import java.io.Serializable; import java.util.Scanner; //import javafx.scene.control.SpinnerValueFactory;

/** *

@author NCT99 */ public class ChiTietHoaDon implements Serializable { private String maSP,maHD; private int soLuong=0; private double giamGia=0.0; SanPham temp=new SanPham(); private int indexSP=-1; public ChiTietHoaDon() { }

public ChiTietHoaDon(String maSP, String maHD, int soLuong, float giamGia) { this.maSP = maSP; this.maHD = maHD; this.soLuong = soLuong; this.giamGia = giamGia; }

public String getMaSP() { return maSP; }

public void setMaSP(String maSP) { this.maSP = maSP; }

public String getMaHD() { return maHD; }

public void setMaHD(String maHD) { this.maHD = maHD; }

public int getSoLuong() { return soLuong; }

public void setSoLuong(int soLuong) { this.soLuong = soLuong; }

public double getGiamGia() { return giamGia; }

public void setGiamGia(float giamGia) { this.giamGia = giamGia; }

@Override public String toString() { return "ChiTietHoaDon{" + "maSP=" + maSP + ", maHD=" + maHD + ", soLuong=" + soLuong + ", giamGia=" + giamGia + '}'; } public void nhapCTHD(DSSP dssp,DSHD dshd){ Scanner sc =new Scanner(System.in); int coHD=-1;//xÃ¡c Ä�á»�nh xem cÃ³ nháº­p Ä�Ãºng mÃ£ hÃ³a Ä�Æ¡n Ä�Ã£ tá»�n táº¡i khÃ´ng. do{ System.out.print("\n Nháº­p mÃ£ hÃ³a Ä�Æ¡n bÃ¡n:"); maHD=sc.nextLine(); for (HoaDonBan x : dshd.listDT) { if(maHD.equals(x.getMaHD())) { coHD=1; break; } } if(coHD!=1) System.out.print("\n!!! Wrong.Trong danh sÃ¡ch hÃ³a Ä�Æ¡n khÃ´ng cÃ³ mÃ£ nÃ y.!!!"); }while(coHD!=1); int coSP=-1;

 do {            
     System.out.print("\n Nháº­p mÃ£ sáº£n pháº©m:");
     maSP=sc.nextLine();
     for (SanPham x : dssp.listDT) {
         if(maSP.equals(x.getMaSP()))
         {
             coSP=1;
             if(x.getSoLuong()<=0)
                 {
                    coSP=-2;
                    break;
                 }
             temp=x;
             indexSP=dssp.listDT.indexOf(x);
             break;
         }
         
     }
     if(coSP==-1)
         System.out.print("\n!!!Trong danh sÃ¡ch sáº£n pháº©m khÃ´ng cÃ³ mÃ£ nÃ y.!!!");
if(coSP==-2) System.out.print("\n!!!Sáº£n pháº©m nÃ y Ä�Ã£ háº¿t hÃ ng.!!!"); } while (coSP!=1); do {
System.out.print("\n Nháº­p sá»� lÆ°á»£ng mua sáº£n pháº©m nÃ y:"); try { soLuong=sc.nextInt(); if(soLuong<=0) System.out.print("\n!!!Wrong. sá»� lÆ°á»£ng pháº£i lá»�n hÆ¡n khÃ´ng.!!!"); if(temp.getSoLuong()<soLuong) System.out.print("\n!!!Sá»� lÆ°á»£ng nháº­p vÃ o lá»�n hÆ¡n sá»� lÆ°á»£ng hiá»�n cÃ³ cá»§a sáº£n pháº©m trong danh sÃ¡ch.!!");

            sc.nextLine();
        } catch (Exception e) {
            System.out.print("\n!!Lá»�i:"+e+" ; nháº­p vÃ o sá»� nguyÃªn.");
            sc.nextLine();
        }

        
    } while (soLuong<=0 || temp.getSoLuong()<soLuong);
    //cáº­p nháº­t láº¡i sá»� lÆ°á»£ng cho sáº£n pháº©m Ä�ang nháº­p nÃ y.
    dssp.listDT.get(indexSP).setSoLuong(dssp.listDT.get(indexSP).getSoLuong()-this.soLuong);
    
    do {            
        System.out.print("\n Nháº­p giáº£m giÃ¡ (0 -> 100)%:");
        try {
            giamGia=sc.nextFloat();
        
        if(giamGia<0 ||giamGia>100)
            System.out.print("\n!!Wrong. nháº­p má»©c giáº£m giÃ¡ sai.!!!");
        sc.nextLine();
        } catch (Exception e) {
            System.out.print("\n!!Lá»�i:"+e+" ; nháº­p vÃ o sá»� nguyÃªn.");
            sc.nextLine();
        }
    } while (giamGia<0 ||giamGia>100);
}
public void xuat(){
    System.out.format("\n%-10s%-10s%-10d%-10.2f%-15.3f", maHD,maSP,soLuong,giamGia,ThanhTien());
}
public double ThanhTien(){
    return soLuong*temp.getDonGiaBan()-soLuong*temp.getDonGiaBan()*giamGia/100;
}
}​

About
No description, website, or topics provided.
Resources
 Readme
 Activity
Stars
 0 stars
Watchers
 1 watching
Forks
 0 forks
Releases
No releases published
Create a new release
Packages
No packages published
Publish your first package
Footer
©
