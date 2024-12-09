if(coSP==-2)
                System.out.print("\n!!!Sáº£n pháº©m nÃ y ÄÃ£ háº¿t hÃ ng.!!!");
        } while (coSP!=1);
        do {            
            System.out.print("\n Nháº­p sá» lÆ°á»£ng mua sáº£n pháº©m nÃ y:");
            try {
                soLuong=sc.nextInt();
                if(soLuong<=0)
                    System.out.print("\n!!!Wrong. sá» lÆ°á»£ng pháº£i lá»n hÆ¡n khÃ´ng.!!!");
                if(temp.getSoLuong()<soLuong)
                    System.out.print("\n!!!Sá» lÆ°á»£ng nháº­p vÃ o lá»n hÆ¡n sá» lÆ°á»£ng hiá»n cÃ³ cá»§a sáº£n pháº©m trong danh sÃ¡ch.!!");
            
                sc.nextLine();
            } catch (Exception e) {
                System.out.print("\n!!Lá»i:"+e+" ; nháº­p vÃ o sá» nguyÃªn.");
                sc.nextLine();
            }

            
        } while (soLuong<=0 || temp.getSoLuong()<soLuong);
        //cáº­p nháº­t láº¡i sá» lÆ°á»£ng cho sáº£n pháº©m Äang nháº­p nÃ y.
        dssp.listDT.get(indexSP).setSoLuong(dssp.listDT.get(indexSP).getSoLuong()-this.soLuong);
        
        do {            
            System.out.print("\n Nháº­p giáº£m giÃ¡ (0 -> 100)%:");
            try {
                giamGia=sc.nextFloat();
            
            if(giamGia<0 ||giamGia>100)
                System.out.print("\n!!Wrong. nháº­p má»©c giáº£m giÃ¡ sai.!!!");
            sc.nextLine();
            } catch (Exception e) {
                System.out.print("\n!!Lá»i:"+e+" ; nháº­p vÃ o sá» nguyÃªn.");
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
}
