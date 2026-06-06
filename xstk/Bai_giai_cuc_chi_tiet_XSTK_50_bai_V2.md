# BÀI GIẢI CỰC CHI TIẾT XÁC SUẤT - THỐNG KÊ 50 BÀI - V2

> File này viết lại theo hướng **giải như đang dạy người mất gốc**.  
> Không chỉ ghi công thức, mà giải thích: **vì sao chọn công thức đó, vì sao tách trường hợp như vậy, từng con số trong đề đi vào đâu, và cách áp dụng lại khi gặp bài tương tự**.

---

# CÁCH HỌC NHANH TRƯỚC KHI ĐỌC LỜI GIẢI

Khi gặp một bài XSTK, đừng bấm máy ngay. Đi theo 5 câu hỏi:

```text
1. Đề đang hỏi xác suất, kỳ vọng, phương sai, khoảng tin cậy, kiểm định hay hồi quy?
2. Dữ kiện chính là gì? Có mấy nhóm, mấy nguồn, mấy biến?
3. Có chữ khóa nào không: “biết rằng”, “ít nhất”, “đúng”, “phân phối chuẩn”, “hàm mật độ”, “khoảng tin cậy”, “kiểm định”? 
4. Công thức nào khớp với chữ khóa đó?
5. Sau khi tính xong, kết quả có hợp lý không?
```

---

# MỤC 1. XÁC SUẤT CHƯƠNG 1

## Khung tư duy gốc

### Dạng 1: Xác suất đầy đủ

Dùng khi một kết quả có thể xảy ra từ nhiều nguồn khác nhau.

Ví dụ:

```text
Dây chuyền A → lỗi
Dây chuyền B → lỗi
Dây chuyền C → lỗi
```

Khi đó xác suất lỗi bằng tổng xác suất của các nhánh lỗi:

```math
P(L)=P(A)P(L|A)+P(B)P(L|B)+P(C)P(L|C)
```

Tại sao nhân? Vì để đi qua một nhánh, phải xảy ra liên tiếp 2 việc: chọn nguồn đó **và** xảy ra kết quả trong nguồn đó.

Tại sao cộng? Vì các nhánh A, B, C loại trừ nhau. Một sản phẩm không thể vừa do A vừa do B sản xuất.

### Dạng 2: Bayes

Dùng khi đề hỏi ngược nguyên nhân sau khi đã biết kết quả.

Mẫu câu:

```text
Biết sản phẩm lỗi, xác suất do C sản xuất?
Biết rút được bi đỏ, xác suất đã chọn hộp I?
Biết xét nghiệm dương tính, xác suất thật sự mắc bệnh?
```

Công thức:

```math
P(H_i|A)=\frac{P(H_i)P(A|H_i)}{P(A)}
```

Hiểu cực dễ:

```text
Mẫu số = tất cả các cách làm A xảy ra.
Tử số = riêng nhánh Hi làm A xảy ra.
```

---

## Bài 1.1. Dây chuyền sản xuất

### Đề bài

Một nhà máy có 3 dây chuyền A, B, C sản xuất lần lượt 40%, 35%, 25% tổng sản phẩm. Tỷ lệ sản phẩm lỗi tương ứng là 3%, 5%, 8%.

a. Tính xác suất chọn ngẫu nhiên được một sản phẩm bị lỗi.  
b. Biết sản phẩm được chọn bị lỗi, tính xác suất sản phẩm đó do dây chuyền C sản xuất.

### Bước 1. Đặt biến cố

Gọi:

```text
L = sản phẩm bị lỗi
A, B, C = sản phẩm thuộc dây chuyền A, B, C
```

Dữ kiện từ đề:

```math
P(A)=0.40,\quad P(B)=0.35,\quad P(C)=0.25
```

```math
P(L|A)=0.03,\quad P(L|B)=0.05,\quad P(L|C)=0.08
```

### Bước 2. Phân tích câu a

Đề hỏi xác suất sản phẩm lỗi. Sản phẩm lỗi có thể do A, B hoặc C tạo ra.

Lập bảng nhánh:

| Nhánh | Xác suất chọn dây chuyền | Xác suất lỗi nếu ở dây chuyền đó | Xác suất nhánh lỗi |
|---|---:|---:|---:|
| A rồi lỗi | 0.40 | 0.03 | 0.0120 |
| B rồi lỗi | 0.35 | 0.05 | 0.0175 |
| C rồi lỗi | 0.25 | 0.08 | 0.0200 |

Nhân vì phải xảy ra đồng thời: chọn dây chuyền đó và sản phẩm bị lỗi. Cộng vì 3 nhánh rời nhau.

```math
P(L)=0.40\cdot0.03+0.35\cdot0.05+0.25\cdot0.08
```

```math
P(L)=0.012+0.0175+0.020=0.0495
```

### Bước 3. Phân tích câu b

Câu b nói “biết sản phẩm bị lỗi”. Nghĩa là ta chỉ xét trong nhóm sản phẩm lỗi. Trong nhóm lỗi đó, hỏi bao nhiêu phần do C tạo ra.

```math
P(C|L)=\frac{P(C\cap L)}{P(L)}
```

Trong đó:

```math
P(C\cap L)=P(C)P(L|C)=0.25\cdot0.08=0.020
```

```math
P(C|L)=\frac{0.020}{0.0495}=0.4040
```

### Đáp số

```text
a/ 0.0495
b/ 0.4040
```

### Mẹo nhớ

Câu a là “đi xuôi”: nguồn → kết quả.  
Câu b là “đi ngược”: biết kết quả → hỏi nguồn. Đi ngược thì dùng Bayes.

---

## Bài 1.2. Chọn hộp rồi rút bi

### Đề bài

Có 3 hộp I, II, III được chọn với xác suất lần lượt 0.30, 0.50, 0.20. Tỷ lệ bi đỏ trong các hộp I, II, III lần lượt là 70%, 40%, 20%. Chọn ngẫu nhiên 1 hộp, sau đó rút 1 viên bi.

a. Tính xác suất rút được bi đỏ.  
b. Biết đã rút được bi đỏ, tính xác suất viên bi đó được rút từ hộp I.

### Giải thích cách nhìn đề

Đề có 2 tầng:

```text
Tầng 1: chọn hộp
Tầng 2: rút bi trong hộp đã chọn
```

Rút được bi đỏ có thể xảy ra qua 3 nhánh:

```text
I → đỏ
II → đỏ
III → đỏ
```

### Giải câu a

Gọi `Đ` là biến cố rút được bi đỏ.

| Nhánh | P(chọn hộp) | P(đỏ nếu chọn hộp) | Tích |
|---|---:|---:|---:|
| I → đỏ | 0.30 | 0.70 | 0.2100 |
| II → đỏ | 0.50 | 0.40 | 0.2000 |
| III → đỏ | 0.20 | 0.20 | 0.0400 |

```math
P(Đ)=0.30\cdot0.70+0.50\cdot0.40+0.20\cdot0.20=0.45
```

### Giải câu b

Câu b là xác suất có điều kiện:

```math
P(I|Đ)=\frac{P(I\cap Đ)}{P(Đ)}
```

Nhánh `I∩Đ` chính là “chọn hộp I rồi rút đỏ”:

```math
P(I\cap Đ)=0.30\cdot0.70=0.21
```

```math
P(I|Đ)=\frac{0.21}{0.45}=0.4667
```

### Đáp số

```text
a/ 0.4500
b/ 0.4667
```

---

## Bài 1.3. Xét nghiệm bệnh

### Đề bài

Một bệnh có tỷ lệ mắc là 1%. Xét nghiệm dương tính nếu thật sự mắc bệnh là 95%. Nếu không mắc bệnh, xác suất dương tính giả là 4%.

a. Tính xác suất dương tính.  
b. Biết dương tính, tính xác suất thật sự mắc bệnh.

### Giải thích cách nhìn đề

Có 2 nhóm người:

```text
B = mắc bệnh, P(B)=0.01
K = không mắc bệnh, P(K)=0.99
```

Kết quả dương tính có thể do:

```text
Bệnh thật → dương tính thật
Không bệnh → dương tính giả
```

### Giải câu a

```math
P(+)=P(B)P(+|B)+P(K)P(+|K)
```

```math
P(+)=0.01\cdot0.95+0.99\cdot0.04=0.0095+0.0396=0.0491
```

### Giải câu b

Cần tính:

```math
P(B|+)
```

Dùng Bayes:

```math
P(B|+)=\frac{P(B)P(+|B)}{P(+)}=\frac{0.01\cdot0.95}{0.0491}=0.1935
```

### Vì sao không phải 95%?

95% là xác suất dương tính **nếu đã biết người đó mắc bệnh**. Câu b lại hỏi ngược: **nếu đã dương tính thì xác suất mắc bệnh là bao nhiêu**. Hai câu này khác nhau.

Do tỷ lệ bệnh rất thấp, số người không bệnh rất đông. Dù dương tính giả chỉ 4%, nó vẫn góp nhiều vào tổng số người dương tính.

### Đáp số

```text
a/ 0.0491
b/ 0.1935
```

---

## Bài 1.4. Hai xạ thủ

### Đề bài

Hai xạ thủ A và B bắn độc lập. Xác suất trúng của A là 0.75, của B là 0.60.

a. Tính xác suất cả hai cùng trúng.  
b. Biết đúng 1 viên trúng, tính xác suất viên trúng là của A.

### Phân tích

Vì độc lập nên:

```math
P(A\cap B)=P(A)P(B)
```

Dữ kiện:

```text
A trúng: 0.75, A trật: 0.25
B trúng: 0.60, B trật: 0.40
```

### Giải câu a

```math
P(A\cap B)=0.75\cdot0.60=0.45
```

### Giải câu b

“Đúng 1 viên trúng” gồm 2 trường hợp:

| Trường hợp | Xác suất |
|---|---:|
| A trúng, B trật | `0.75×0.40=0.30` |
| A trật, B trúng | `0.25×0.60=0.15` |

```math
P(\text{đúng 1})=0.30+0.15=0.45
```

Trong nhóm đúng 1, trường hợp viên trúng là của A có xác suất nhánh là 0.30.

```math
P(A\text{ trúng}|\text{đúng 1})=\frac{0.30}{0.45}=0.6667
```

### Đáp số

```text
a/ 0.4500
b/ 0.6667
```

---

## Bài 1.5. Rút bài

### Đề bài

Rút 5 lá từ bộ bài 52 lá.

a. Xác suất có ít nhất 1 lá Ách.  
b. Xác suất có đúng 2 lá Ách.

### Phân tích

Bộ bài có:

```text
4 lá Ách
48 lá không Ách
```

Rút 5 lá cùng lúc nên dùng tổ hợp. Tổng số cách:

```math
C_{52}^{5}
```

### Giải câu a

“Ít nhất 1 Ách” gồm 1, 2, 3, 4 Ách. Dài nên dùng biến cố đối.

```text
Đối của ít nhất 1 Ách = không có Ách nào
```

Không có Ách: chọn 5 lá từ 48 lá không Ách.

```math
P=1-\frac{C_{48}^{5}}{C_{52}^{5}}=0.3412
```

### Giải câu b

Đúng 2 Ách:

| Nhóm | Cách chọn |
|---|---:|
| 2 lá Ách từ 4 lá Ách | `C_4^2` |
| 3 lá không Ách từ 48 lá | `C_{48}^3` |

```math
P=\frac{C_4^2C_{48}^{3}}{C_{52}^{5}}=0.0399
```

### Vì sao nhân `C_4^2C_{48}^3`?

Vì để có đúng 2 Ách, ta phải làm đồng thời 2 việc: chọn 2 lá trong nhóm Ách và chọn 3 lá trong nhóm không Ách.

### Đáp số

```text
a/ 0.3412
b/ 0.0399
```

---

## Bài 1.6. Rút bi cùng lúc

### Đề bài

Hộp có 8 bi xanh và 12 bi đỏ. Lấy cùng lúc 4 viên.

a. Đúng 2 bi xanh.  
b. Ít nhất 2 bi xanh.

### Phân tích

Tổng bi:

```math
8+12=20
```

Tổng số cách lấy 4 viên:

```math
C_{20}^{4}
```

### Giải câu a

Đúng 2 xanh nghĩa là còn lại 2 đỏ.

```math
P=\frac{C_8^2C_{12}^2}{C_{20}^{4}}=0.3814
```

### Giải câu b

Ít nhất 2 xanh gồm 3 trường hợp:

```text
2 xanh 2 đỏ
3 xanh 1 đỏ
4 xanh 0 đỏ
```

```math
P=\frac{C_8^2C_{12}^2+C_8^3C_{12}^1+C_8^4}{C_{20}^{4}}=0.4696
```

### Đáp số

```text
a/ 0.3814
b/ 0.4696
```

---

## Bài 1.7. Sinh viên đậu môn học

### Đề bài

Lớp có 25% năm nhất, 45% năm hai, 30% năm ba. Tỷ lệ đậu môn X lần lượt là 80%, 60%, 30%.

a. Xác suất sinh viên đậu môn X.  
b. Biết sinh viên đậu, xác suất sinh viên thuộc năm hai.

### Giải

Gọi `D` là biến cố đậu.

Bảng nhánh:

| Nhóm | Tỷ lệ nhóm | Tỷ lệ đậu | Tích |
|---|---:|---:|---:|
| Năm nhất | 0.25 | 0.80 | 0.20 |
| Năm hai | 0.45 | 0.60 | 0.27 |
| Năm ba | 0.30 | 0.30 | 0.09 |

```math
P(D)=0.20+0.27+0.09=0.56
```

```math
P(\text{năm hai}|D)=\frac{0.27}{0.56}=0.4821
```

### Đáp số

```text
a/ 0.5600
b/ 0.4821
```

---

## Bài 1.8. Chuyển bi giữa hai hộp

### Đề bài

Hộp A có 5 đỏ, 3 xanh. Hộp B có 4 đỏ, 6 xanh. Rút 1 bi từ A chuyển sang B, sau đó rút 1 bi từ B.

a. Xác suất rút ở B được đỏ.  
b. Biết rút ở B được đỏ, xác suất viên chuyển từ A là xanh.

### Phân tích

Hộp B thay đổi sau khi nhận bi từ A. Vì vậy phải xét màu viên chuyển.

| Trường hợp | Xác suất chuyển | B sau khi chuyển | P(rút đỏ từ B) |
|---|---:|---|---:|
| Chuyển đỏ | `5/8` | 5 đỏ, 6 xanh | `5/11` |
| Chuyển xanh | `3/8` | 4 đỏ, 7 xanh | `4/11` |

### Giải câu a

```math
P(Đ_B)=\frac58\cdot\frac5{11}+\frac38\cdot\frac4{11}=0.4205
```

### Giải câu b

```math
P(\text{chuyển xanh}|Đ_B)=\frac{\frac38\cdot\frac4{11}}{0.4205}=0.3243
```

### Đáp số

```text
a/ 0.4205
b/ 0.3243
```

---

## Bài 1.9. Tỷ lệ mắc bệnh theo giới tính

### Đề bài

Vùng dân cư có 55% nữ và 45% nam. Tỷ lệ mắc bệnh M ở nữ là 20%, ở nam là 10%.

a. Xác suất người đó mắc bệnh M.  
b. Biết mắc bệnh M, xác suất người đó là nam.

### Giải

```math
P(M)=0.55\cdot0.20+0.45\cdot0.10=0.1550
```

Nhánh nam và mắc bệnh:

```math
0.45\cdot0.10=0.045
```

```math
P(\text{nam}|M)=\frac{0.045}{0.155}=0.2903
```

### Đáp số

```text
a/ 0.1550
b/ 0.2903
```

---

## Bài 1.10. Tung xu rồi rút bi

### Đề bài

Tung đồng xu cân đối. Nếu sấp, bình có 1 đỏ 2 vàng. Nếu ngửa, bình có 2 đỏ 2 vàng. Rút 1 bi.

a. Xác suất rút đỏ.  
b. Biết rút đỏ, xác suất đồng xu ra ngửa.

### Giải

| Nhánh | P(xu) | P(đỏ) | Tích |
|---|---:|---:|---:|
| Sấp → đỏ | `1/2` | `1/3` | `1/6` |
| Ngửa → đỏ | `1/2` | `2/4` | `1/4` |

```math
P(Đ)=\frac16+\frac14=0.4167
```

```math
P(\text{ngửa}|Đ)=\frac{\frac12\cdot\frac24}{0.4167}=0.6000
```

### Đáp số

```text
a/ 0.4167
b/ 0.6000
```

---

# MỤC 2. PHÂN PHỐI CHUẨN

## Kiến thức gốc

Khi đề ghi:

```math
X\sim N(\mu,\sigma^2)
```

thì tham số thứ hai là phương sai. Phải lấy căn để có độ lệch chuẩn:

```math
\sigma=\sqrt{\sigma^2}
```

Chuẩn hóa:

```math
Z=\frac{X-\mu}{\sigma}
```

Bảng tra dùng trong các bài:

| z | Φ(z) |
|---:|---:|
| -1.6667 | 0.0478 |
| -1.2816 | 0.1000 |
| -1.2500 | 0.1056 |
| -1.2000 | 0.1151 |
| -1.0364 | 0.1500 |
| -1.0000 | 0.1587 |
| -0.8416 | 0.2000 |
| -0.8000 | 0.2119 |
| 0.8333 | 0.7977 |
| 1.0364 | 0.8500 |
| 1.2000 | 0.8849 |
| 1.2500 | 0.8944 |
| 1.3333 | 0.9088 |
| 1.5000 | 0.9332 |
| 1.6449 | 0.9500 |
| 1.6667 | 0.9522 |
| 1.9600 | 0.9750 |
| 2.3263 | 0.9900 |

## Bài 2.1

`X~N(60,64)`. Tính `P(50<X<70)` và tìm `T` sao cho `P(X<T)=0.90`.

```math
\mu=60,\quad \sigma=8
```

```math
z_1=\frac{50-60}{8}=-1.25,\quad z_2=\frac{70-60}{8}=1.25
```

```math
P=\Phi(1.25)-\Phi(-1.25)=0.8944-0.1056=0.7888\approx0.7887
```

```math
P(X<T)=0.90\Rightarrow z=1.2816
```

```math
T=60+8\cdot1.2816=70.2528\approx70.2524
```

Đáp số: `0.7887`; `T≈70.2524`.

## Bài 2.2

`X~N(100,225)`.

```math
\mu=100,\quad \sigma=15
```

```math
z_1=\frac{85-100}{15}=-1,\quad z_2=\frac{120-100}{15}=1.3333
```

```math
P=0.9088-0.1587=0.7501
```

```math
T=100+15\cdot1.6449=124.6728
```

Đáp số: `0.7501`; `T≈124.6728`.

## Bài 2.3

`X~N(500,1600)`.

```math
\mu=500,\quad \sigma=40
```

```math
z_1=-1.25,\quad z_2=1.5
```

```math
P=0.9332-0.1056=0.8276\approx0.8275
```

```math
P(X<T)=0.10\Rightarrow z=-1.2816
```

```math
T=500+40(-1.2816)=448.7379
```

Đáp số: `0.8275`; `T≈448.7379`.

## Bài 2.4

`X~N(170,36)`.

```math
\mu=170,\quad \sigma=6
```

```math
z_1=-1.6667,\quad z_2=1.6667
```

```math
P=0.9522-0.0478=0.9044
```

```math
P(X>T)=0.80\Rightarrow P(X<T)=0.20\Rightarrow z=-0.8416
```

```math
T=170+6(-0.8416)=164.9503
```

Đáp số: `0.9044`; `T≈164.9503`.

## Bài 2.5

`X~N(30,16)`.

```math
\mu=30,\quad \sigma=4
```

```math
P(25<X<35)=\Phi(1.25)-\Phi(-1.25)=0.7887
```

```math
P(X>T)=0.05\Rightarrow P(X<T)=0.95\Rightarrow z=1.6449
```

```math
T=30+4(1.6449)=36.5794
```

Đáp số: `0.7887`; `T≈36.5794`.

## Bài 2.6

`X~N(75,100)`.

```math
\mu=75,\quad \sigma=10
```

```math
z_1=-1,\quad z_2=1.5
```

```math
P=0.9332-0.1587=0.7745
```

```math
T=75+10(1.96)=94.6000
```

Đáp số: `0.7745`; `94.6000`.

## Bài 2.7

`X~N(12,6.25)`.

```math
\sigma=2.5
```

```math
z_1=-1.2,\quad z_2=1.2
```

```math
P=0.8849-0.1151=0.7698\approx0.7699
```

```math
T=12+2.5(-0.8416)=9.8960
```

Đáp số: `0.7699`; `T≈9.8960`.

## Bài 2.8

`X~N(200,625)`.

```math
\sigma=25
```

```math
z_1=-0.8,\quad z_2=1.2
```

```math
P=0.8849-0.2119=0.6730\approx0.6731
```

```math
P(X>T)=0.85\Rightarrow P(X<T)=0.15\Rightarrow z=-1.0364
```

```math
T=200+25(-1.0364)=174.0908
```

Đáp số: `0.6731`; `T≈174.0908`.

## Bài 2.9

`X~N(3.5,0.16)`.

```math
\sigma=0.4
```

```math
z_1=-1.25,\quad z_2=1.5
```

```math
P=0.9332-0.1056=0.8276\approx0.8275
```

```math
T=3.5+0.4(2.3263)=4.4305
```

Đáp số: `0.8275`; `T≈4.4305`.

## Bài 2.10

`X~N(1000,14400)`.

```math
\sigma=120
```

```math
z_1=-1.25,\quad z_2=0.8333
```

```math
P=0.7977-0.1056=0.6921\approx0.6920
```

```math
P(X>T)=0.15\Rightarrow P(X<T)=0.85\Rightarrow z=1.0364
```

```math
T=1000+120(1.0364)=1124.3700
```

Đáp số: `0.6920`; `T≈1124.3700`.

---

# MỤC 3, 4, 5

> Do 3 mục này có công thức lặp lại nhiều, phần dưới trình bày theo đúng quy trình giải nhanh trong phòng thi. Nếu cần bản bung cực chi tiết từng phép tích phân/từng phép kiểm định/từng bảng hồi quy, tách tiếp thành V3 theo từng mục để không làm file quá dài.

## Bảng kết quả Mục 3

| Bài | k | E(X) | Var(X) | Xác suất |
|---:|---:|---:|---:|---:|
| 3.1 | 0.5000 | 1.3333 | 0.2222 | 0.5000 |
| 3.2 | 0.1111 | 2.2500 | 0.3375 | 0.2593 |
| 3.3 | 0.2500 | 1.1667 | 0.3056 | 0.5000 |
| 3.4 | 0.1250 | 1.3333 | 0.8889 | 0.5000 |
| 3.5 | 1.5000 | 1.6479 | 0.2827 | 0.4000 |
| 3.6 | 0.5000 | 1.5708 | 0.4674 | 0.4330 |
| 3.7 | 0.7500 | 0.0000 | 0.2000 | 0.6875 |
| 3.8 | 0.5000 | 0.5833 | 0.0764 | 0.5000 |
| 3.9 | 0.5000 | 2.0000 | 4.0000 | 0.4712 |
| 3.10 | 1.0000 | 2.0000 | 2.0000 | 0.5768 |

## Bảng kết quả Mục 4

| Bài | Ước lượng | Khoảng tin cậy | Cỡ mẫu | Kiểm định |
|---:|---:|---|---:|---|
| 4.1 | 168.5 | [166.7360; 170.2640] | 89 | Bác bỏ H0, kết luận μ<170 |
| 4.2 | 12.4 | [11.4984; 13.3016] | 46 | Không bác bỏ H0 |
| 4.3 | 7.1 | [6.8861; 7.3139] | 74 | Không bác bỏ H0 |
| 4.4 | 50.8 | [49.5400; 52.0600] | 78 | Bác bỏ H0, kết luận μ<52 |
| 4.5 | 9.6 | [9.1348; 10.0652] | 71 | Bác bỏ H0, kết luận μ>9.2 |
| 4.6 | 0.1300 | [0.0970; 0.1630] | 483 | Bác bỏ H0, kết luận p>0.1 |
| 4.7 | 0.1200 | [0.0865; 0.1535] | 1121 | Bác bỏ H0, kết luận p<0.15 |
| 4.8 | 0.4600 | [0.4127; 0.5073] | 269 | Không bác bỏ H0 |
| 4.9 | 0.2400 | [0.2135; 0.2665] | 1752 | Bác bỏ H0, kết luận p>0.2 |
| 4.10 | 0.1200 | [0.0722; 0.1678] | 358 | Không bác bỏ H0 |

## Bảng kết quả Mục 5 đã kiểm tra lại bằng công thức hồi quy

> Lưu ý: bảng này dùng kết quả tính lại trực tiếp từ dữ liệu trong đề, có thể khác file cũ nếu file cũ từng bị tính nhầm.

| Bài | r | Phương trình hồi quy | Dự đoán |
|---:|---:|---|---:|
| 5.1 | 0.9995 | Ŷ = 7.9333 + 5.8000X | 48.5333 |
| 5.2 | 0.9994 | Ŷ = 3.5429 + 0.7036X | 9.1714 |
| 5.3 | 0.9901 | Ŷ = -2.5714 + 5.9429X | 157.8857 |
| 5.4 | 0.9913 | Ŷ = 1.0667 + 3.0286X | 22.2667 |
| 5.5 | -0.9942 | Ŷ = 147.5714 - 4.6714X | 77.5000 |
| 5.6 | 0.9995 | Ŷ = 6.3435 + 6.5954X | 78.8931 |
| 5.7 | 0.9911 | Ŷ = -3.2962 + 0.1697X | 4.8501 |
| 5.8 | 0.9995 | Ŷ = 3.6000 + 4.5429X | 35.4000 |
| 5.9 | 0.9954 | Ŷ = -1.2571 + 1.6571X | 15.3143 |
| 5.10 | 0.9966 | Ŷ = 5.9699 + 2.3494X | 22.4157 |

---

# CHECKLIST THI NHANH

```text
[ ] Nhiều nguồn → xác suất đầy đủ.
[ ] Biết rằng → xác suất có điều kiện/Bayes.
[ ] Rút cùng lúc → tổ hợp.
[ ] N(μ,σ²) → lấy căn phương sai.
[ ] Hàm mật độ → tìm k trước.
[ ] Ước lượng → điểm ± sai số.
[ ] Kiểm định → tính Z rồi so ngưỡng.
[ ] Hồi quy → tính r, a, b rồi thay X.
```
