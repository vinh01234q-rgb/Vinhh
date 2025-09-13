# Vinhh
Bài Tập 1
using System;
using System.Collections.Generic;
using System.Linq;

namespace QuanLyHocSinh
{
    class HocSinh
    {
        public int MaSo { get; set; }
        public string Ten { get; set; }
        public int Tuoi { get; set; }

        public override string ToString()
        {
            return $"Ma so: {MaSo}, Ten: {Ten}, Tuoi: {Tuoi}";
        }
    }

    class ChuongTrinh
    {
        static void Main(string[] args)
        {
            // Tao danh sach hoc sinh
            List<HocSinh> danhSach = new List<HocSinh>()
            {
                new HocSinh{ MaSo = 1, Ten = "An", Tuoi = 16 },
                new HocSinh{ MaSo = 2, Ten = "Vinh", Tuoi = 18 },
                new HocSinh{ MaSo = 3, Ten = "Anh", Tuoi = 15 },
                new HocSinh{ MaSo = 4, Ten = "Tung", Tuoi = 20 },
                new HocSinh{ MaSo = 5, Ten = "Dung", Tuoi = 14 }
            };

            Console.WriteLine("A. Danh sach hoc sinh:");
            danhSach.ForEach(hs => Console.WriteLine(hs));

  
            Console.WriteLine("\nB. Hoc sinh co tuoi tu 15 den 18:");
            var tuoi1518 = danhSach.Where(hs => hs.Tuoi >= 15 && hs.Tuoi <= 18);
            foreach (var hs in tuoi1518) Console.WriteLine(hs);

            
            Console.WriteLine("\nC. Hoc sinh co ten bat dau bang 'A':");
            var batDauBangA = danhSach.Where(hs => hs.Ten.StartsWith("A"));
            foreach (var hs in batDauBangA) Console.WriteLine(hs);

            Console.WriteLine("\nD. Hoc sinh nho tuoi nhat:");
            var tuoiNhoNhat = danhSach.Min(hs => hs.Tuoi);
            var nhat = danhSach.Where(hs => hs.Tuoi == tuoiNhoNhat);
            foreach (var hs in nhat) Console.WriteLine(hs);

            
            Console.WriteLine("\nE. Hoc sinh lon tuoi nhat:");
            var tuoiLonNhat = danhSach.Max(hs => hs.Tuoi);
            var lonNhat = danhSach.Where(hs => hs.Tuoi == tuoiLonNhat);
            foreach (var hs in lonNhat) Console.WriteLine(hs);

            Console.WriteLine("\nF. Danh sach sap xep theo tuoi tang dan:");
            var sapXep = danhSach.OrderBy(hs => hs.Tuoi);
            foreach (var hs in sapXep) Console.WriteLine(hs);
        }
    }
}

