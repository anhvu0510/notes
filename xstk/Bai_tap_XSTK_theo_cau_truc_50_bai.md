# BỘ BÀI TẬP XÁC SUẤT - THỐNG KÊ

> Bộ bài được thiết kế theo đúng cấu trúc đề: 5 mục lớn, mỗi mục 10 bài.  
> Tổng cộng: **50 bài tập**.  
> Riêng **Mục 3** chỉ dùng **biến ngẫu nhiên liên tục 1 biến**.

---

## Mục lục nhanh

| Mục | Nội dung | Số bài |
|---:|---|---:|
| 1 | Xác suất chương 1: xác suất đầy đủ, Bayes, xác suất có điều kiện | 10 |
| 2 | Biến ngẫu nhiên liên tục phân phối chuẩn | 10 |
| 3 | Biến ngẫu nhiên liên tục 1 biến: mật độ, kỳ vọng, phương sai | 10 |
| 4 | Ước lượng và kiểm định thống kê | 10 |
| 5 | Tương quan và hồi quy tuyến tính | 10 |

---

# MỤC 1. XÁC SUẤT CHƯƠNG 1

> Trọng tâm: công thức xác suất đầy đủ, công thức Bayes, xác suất có điều kiện, biến cố độc lập, tổ hợp cơ bản.

## Bài 1.1. Dây chuyền sản xuất

Một nhà máy có 3 dây chuyền A, B, C sản xuất lần lượt **40%**, **35%**, **25%** tổng sản phẩm. Tỷ lệ sản phẩm lỗi tương ứng là **3%**, **5%**, **8%**.

Yêu cầu:

a. Tính xác suất chọn ngẫu nhiên được một sản phẩm bị lỗi.  
b. Biết sản phẩm được chọn bị lỗi, tính xác suất sản phẩm đó do dây chuyền C sản xuất.

---

## Bài 1.2. Chọn hộp rồi rút bi

Có 3 hộp I, II, III được chọn với xác suất lần lượt **0,30**, **0,50**, **0,20**. Tỷ lệ bi đỏ trong các hộp I, II, III lần lượt là **70%**, **40%**, **20%**.

Chọn ngẫu nhiên 1 hộp, sau đó rút ngẫu nhiên 1 viên bi.

Yêu cầu:

a. Tính xác suất rút được bi đỏ.  
b. Biết đã rút được bi đỏ, tính xác suất viên bi đó được rút từ hộp I.

---

## Bài 1.3. Xét nghiệm bệnh

Một bệnh có tỷ lệ mắc trong cộng đồng là **1%**. Một loại xét nghiệm có xác suất cho kết quả dương tính nếu người đó thật sự mắc bệnh là **95%**. Nếu người đó không mắc bệnh, xác suất xét nghiệm vẫn cho dương tính giả là **4%**.

Yêu cầu:

a. Tính xác suất một người được chọn ngẫu nhiên có kết quả xét nghiệm dương tính.  
b. Biết kết quả xét nghiệm là dương tính, tính xác suất người đó thật sự mắc bệnh.

---

## Bài 1.4. Hai xạ thủ

Hai xạ thủ A và B bắn độc lập vào cùng một mục tiêu. Xác suất bắn trúng của A là **0,75**, của B là **0,60**.

Yêu cầu:

a. Tính xác suất cả hai xạ thủ cùng bắn trúng.  
b. Biết chỉ có đúng 1 viên đạn trúng mục tiêu, tính xác suất viên đạn trúng là của A.

---

## Bài 1.5. Rút bài

Rút ngẫu nhiên 5 lá bài từ bộ bài chuẩn 52 lá.

Yêu cầu:

a. Tính xác suất có ít nhất 1 lá Ách.  
b. Tính xác suất có đúng 2 lá Ách.

---

## Bài 1.6. Rút bi cùng lúc

Một hộp có **8 bi xanh** và **12 bi đỏ**. Lấy ngẫu nhiên cùng lúc 4 viên bi.

Yêu cầu:

a. Tính xác suất lấy được đúng 2 bi xanh.  
b. Tính xác suất lấy được ít nhất 2 bi xanh.

---

## Bài 1.7. Sinh viên đậu môn học

Một lớp có **25%** sinh viên năm nhất, **45%** sinh viên năm hai và **30%** sinh viên năm ba. Tỷ lệ đậu môn X của ba nhóm tương ứng là **80%**, **60%**, **30%**.

Chọn ngẫu nhiên một sinh viên trong lớp.

Yêu cầu:

a. Tính xác suất sinh viên đó đậu môn X.  
b. Biết sinh viên đó đậu môn X, tính xác suất sinh viên đó thuộc năm hai.

---

## Bài 1.8. Chuyển bi giữa hai hộp

Hộp A có **5 bi đỏ**, **3 bi xanh**. Hộp B có **4 bi đỏ**, **6 bi xanh**. Rút ngẫu nhiên 1 viên bi từ hộp A chuyển sang hộp B, sau đó rút ngẫu nhiên 1 viên bi từ hộp B.

Yêu cầu:

a. Tính xác suất rút ở hộp B được bi đỏ.  
b. Biết rút ở hộp B được bi đỏ, tính xác suất viên bi chuyển từ hộp A sang hộp B là bi xanh.

---

## Bài 1.9. Tỷ lệ mắc bệnh theo giới tính

Một vùng dân cư có **55% nữ** và **45% nam**. Tỷ lệ mắc bệnh M ở nữ là **20%**, ở nam là **10%**.

Chọn ngẫu nhiên 1 người trong vùng.

Yêu cầu:

a. Tính xác suất người đó mắc bệnh M.  
b. Biết người đó mắc bệnh M, tính xác suất người đó là nam.

---

## Bài 1.10. Tung xu rồi rút bi

Tung một đồng xu cân đối. Nếu đồng xu ra **sấp**, bỏ vào bình 1 bi đỏ và 2 bi vàng. Nếu đồng xu ra **ngửa**, bỏ vào bình 2 bi đỏ và 2 bi vàng. Sau đó rút ngẫu nhiên 1 viên bi từ bình.

Yêu cầu:

a. Tính xác suất rút được bi đỏ.  
b. Biết rút được bi đỏ, tính xác suất đồng xu đã ra ngửa.

---

# MỤC 2. BIẾN NGẪU NHIÊN LIÊN TỤC PHÂN PHỐI CHUẨN

> Trọng tâm: chuẩn hóa biến ngẫu nhiên chuẩn, tính xác suất bằng hàm phân phối chuẩn tắc, tìm ngưỡng T theo điều kiện xác suất.

Quy ước: nếu đề ghi `X ~ N(μ, σ²)`, tham số thứ hai là **phương sai**.

## Bài 2.1

Cho biến ngẫu nhiên `X ~ N(60, 64)`.

Yêu cầu:

a. Tính `P(50 < X < 70)`.  
b. Tìm `T` sao cho `P(X < T) = 0,90`.

---

## Bài 2.2

Cho biến ngẫu nhiên `X ~ N(100, 225)`.

Yêu cầu:

a. Tính `P(85 < X < 120)`.  
b. Tìm `T` sao cho `P(X < T) = 0,95`.

---

## Bài 2.3

Cho biến ngẫu nhiên `X ~ N(500, 1600)`.

Yêu cầu:

a. Tính `P(450 < X < 560)`.  
b. Tìm `T` sao cho `P(X < T) = 0,10`.

---

## Bài 2.4

Cho biến ngẫu nhiên `X ~ N(170, 36)`.

Yêu cầu:

a. Tính `P(160 < X < 180)`.  
b. Tìm `T` sao cho `P(X > T) = 0,80`.

---

## Bài 2.5

Cho biến ngẫu nhiên `X ~ N(30, 16)`.

Yêu cầu:

a. Tính `P(25 < X < 35)`.  
b. Tìm `T` sao cho `P(X > T) = 0,05`.

---

## Bài 2.6

Cho biến ngẫu nhiên `X ~ N(75, 100)`.

Yêu cầu:

a. Tính `P(65 < X < 90)`.  
b. Tìm `T` sao cho `P(X < T) = 0,975`.

---

## Bài 2.7

Cho biến ngẫu nhiên `X ~ N(12, 6.25)`.

Yêu cầu:

a. Tính `P(9 < X < 15)`.  
b. Tìm `T` sao cho `P(X < T) = 0,20`.

---

## Bài 2.8

Cho biến ngẫu nhiên `X ~ N(200, 625)`.

Yêu cầu:

a. Tính `P(180 < X < 230)`.  
b. Tìm `T` sao cho `P(X > T) = 0,85`.

---

## Bài 2.9

Cho biến ngẫu nhiên `X ~ N(3.5, 0.16)`.

Yêu cầu:

a. Tính `P(3.0 < X < 4.1)`.  
b. Tìm `T` sao cho `P(X < T) = 0,99`.

---

## Bài 2.10

Cho biến ngẫu nhiên `X ~ N(1000, 14400)`.

Yêu cầu:

a. Tính `P(850 < X < 1100)`.  
b. Tìm `T` sao cho `P(X > T) = 0,15`.

---

# MỤC 3. BIẾN NGẪU NHIÊN LIÊN TỤC 1 BIẾN

> Trọng tâm: tìm hằng số `k`, kiểm tra hàm mật độ, tính kỳ vọng, phương sai và xác suất bằng tích phân.

Với mỗi bài, ngoài khoảng xác định thì mặc định `f(x)=0`.

## Bài 3.1

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=kx, \quad 0<x<2.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(0.5 < X < 1.5)`.

---

## Bài 3.2

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=kx^2, \quad 0<x<3.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1 < X < 2)`.

---

## Bài 3.3

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k(x+1), \quad 0<x<2.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(0.5 < X < 1.5)`.

---

## Bài 3.4

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k(4-x), \quad 0<x<4.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1 < X < 3)`.

---

## Bài 3.5

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=\frac{k}{x^2}, \quad 1<x<3.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1.5 < X < 2.5)`.

---

## Bài 3.6

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k\sin x, \quad 0<x<\pi.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(\pi/6 < X < \pi/2)`.

---

## Bài 3.7

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k(1-x^2), \quad -1<x<1.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(-0.5 < X < 0.5)`.

---

## Bài 3.8

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k(2x+1), \quad 0<x<1.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(0.25 < X < 0.75)`.

---

## Bài 3.9

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=ke^{-x/2}, \quad x>0.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1 < X < 4)`.

---

## Bài 3.10

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=kxe^{-x}, \quad x>0.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1 < X < 3)`.

---

# MỤC 4. ƯỚC LƯỢNG VÀ KIỂM ĐỊNH THỐNG KÊ

> Trọng tâm: ước lượng điểm, khoảng tin cậy cho kỳ vọng/tỷ lệ, tính cỡ mẫu, kiểm định kỳ vọng và kiểm định tỷ lệ 1 mẫu.

## Bài 4.1. Trung bình chiều cao

Khảo sát 64 quan sát về chiều cao, thu được:

- `n = 64`
- `x̄ = 168.5`
- `s = 7.2`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 95% cho kỳ vọng.  
c. Với độ chính xác `d = 1.5`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 170`, `H1: μ < 170`.

---

## Bài 4.2. Thời gian xử lý

Khảo sát 36 quan sát về thời gian xử lý, thu được:

- `n = 36`
- `x̄ = 12.4`
- `s = 2.1`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 99% cho kỳ vọng.  
c. Với độ chính xác `d = 0.8`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 13`, `H1: μ ≠ 13`.

---

## Bài 4.3. Điểm thi

Khảo sát 100 quan sát về điểm thi, thu được:

- `n = 100`
- `x̄ = 7.1`
- `s = 1.3`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 90% cho kỳ vọng.  
c. Với độ chính xác `d = 0.25`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 7.0`, `H1: μ > 7.0`.

---

## Bài 4.4. Khối lượng sản phẩm

Khảo sát 49 quan sát về khối lượng, thu được:

- `n = 49`
- `x̄ = 50.8`
- `s = 4.5`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 95% cho kỳ vọng.  
c. Với độ chính xác `d = 1.0`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 52`, `H1: μ < 52`.

---

## Bài 4.5. Tuổi thọ pin

Khảo sát 81 quan sát về tuổi thọ pin, thu được:

- `n = 81`
- `x̄ = 9.6`
- `s = 1.8`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 98% cho kỳ vọng.  
c. Với độ chính xác `d = 0.5`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 9.2`, `H1: μ > 9.2`.

---

## Bài 4.6. Tỷ lệ sản phẩm loại A

Khảo sát 400 sản phẩm, có 52 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 95% cho tỷ lệ.  
c. Với độ chính xác `d = 0.03`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.1`, `H1: p > 0.1`.

---

## Bài 4.7. Tỷ lệ lỗi khảo sát 625 mẫu

Khảo sát 625 sản phẩm, có 75 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 99% cho tỷ lệ.  
c. Với độ chính xác `d = 0.025`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.15`, `H1: p < 0.15`.

---

## Bài 4.8. Khảo sát 300 mẫu

Khảo sát 300 sản phẩm, có 138 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 90% cho tỷ lệ.  
c. Với độ chính xác `d = 0.05`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.5`, `H1: p ≠ 0.5`.

---

## Bài 4.9. Khảo sát 1000 mẫu

Khảo sát 1000 sản phẩm, có 240 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 95% cho tỷ lệ.  
c. Với độ chính xác `d = 0.02`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.2`, `H1: p > 0.2`.

---

## Bài 4.10. Khảo sát 250 mẫu

Khảo sát 250 sản phẩm, có 30 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 98% cho tỷ lệ.  
c. Với độ chính xác `d = 0.04`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.1`, `H1: p ≠ 0.1`.

---

# MỤC 5. TƯƠNG QUAN VÀ HỒI QUY TUYẾN TÍNH

> Trọng tâm: tính hệ số tương quan mẫu, nhận xét mức độ tương quan, lập phương trình hồi quy tuyến tính và dự đoán.

## Bài 5.1. Quảng cáo và doanh thu

| X: Chi phí quảng cáo | Y: Doanh thu |
|---:|---:|
| 2 | 20 |
| 3 | 25 |
| 5 | 37 |
| 6 | 42 |
| 8 | 55 |
| 9 | 60 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 7`.

---

## Bài 5.2. Giờ học và điểm thi

| X: Số giờ học | Y: Điểm thi |
|---:|---:|
| 1 | 4.2 |
| 2 | 5.0 |
| 3 | 5.6 |
| 4 | 6.4 |
| 5 | 7.1 |
| 6 | 7.8 |
| 7 | 8.4 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 8`.

---

## Bài 5.3. Nhiệt độ và lượng điện tiêu thụ

| X: Nhiệt độ | Y: Điện tiêu thụ |
|---:|---:|
| 20 | 120 |
| 22 | 128 |
| 24 | 135 |
| 26 | 150 |
| 28 | 165 |
| 30 | 178 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 27`.

---

## Bài 5.4. Tuổi máy và chi phí bảo trì

| X: Tuổi máy | Y: Chi phí bảo trì |
|---:|---:|
| 1 | 5 |
| 2 | 7 |
| 3 | 9 |
| 4 | 13 |
| 5 | 16 |
| 6 | 20 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 7`.

---

## Bài 5.5. Giá bán và số lượng bán

| X: Giá bán | Y: Số lượng bán |
|---:|---:|
| 10 | 100 |
| 12 | 92 |
| 14 | 85 |
| 16 | 70 |
| 18 | 63 |
| 20 | 55 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 15`.

---

## Bài 5.6. Nhân viên và sản lượng

| X: Số nhân viên | Y: Sản lượng |
|---:|---:|
| 5 | 40 |
| 7 | 52 |
| 8 | 58 |
| 10 | 73 |
| 12 | 86 |
| 15 | 105 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 11`.

---

## Bài 5.7. Độ ẩm và tỷ lệ lỗi

| X: Độ ẩm | Y: Tỷ lệ lỗi (%) |
|---:|---:|
| 30 | 2.0 |
| 35 | 2.5 |
| 40 | 3.5 |
| 45 | 4.0 |
| 50 | 5.4 |
| 55 | 6.1 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 48`.

---

## Bài 5.8. Tháng tuổi và khối lượng

| X: Tháng tuổi | Y: Khối lượng |
|---:|---:|
| 1 | 8 |
| 2 | 13 |
| 3 | 17 |
| 4 | 22 |
| 5 | 26 |
| 6 | 31 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 7`.

---

## Bài 5.9. Độ dài chương trình và số lỗi

| X: Độ dài chương trình | Y: Số lỗi |
|---:|---:|
| 3 | 4 |
| 5 | 7 |
| 7 | 10 |
| 9 | 13 |
| 11 | 18 |
| 13 | 20 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 10`.

---

## Bài 5.10. Kinh nghiệm và lương

| X: Kinh nghiệm | Y: Lương |
|---:|---:|
| 1 | 9 |
| 3 | 13 |
| 4 | 15 |
| 6 | 19 |
| 8 | 25 |
| 10 | 30 |

Yêu cầu:

a. Tính hệ số tương quan mẫu và nhận xét.  
b. Lập phương trình hồi quy tuyến tính `Y` theo `X`.  
c. Dự đoán `Y` khi `X = 7`.
