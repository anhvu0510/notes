# BÀI GIẢI CHI TIẾT XÁC SUẤT - THỐNG KÊ

> File này giải thích theo hướng **mất gốc vẫn đọc được**: nhận diện dạng bài, vì sao dùng công thức đó, thay số từng bước và kết luận rõ ràng.

Quy ước:

- Kết quả xác suất làm tròn 4 chữ số nếu không yêu cầu khác.
- `C(n,k)` là tổ hợp, tức số cách chọn `k` phần tử từ `n` phần tử, **không xét thứ tự**.
- Với phân phối chuẩn `X ~ N(μ, σ²)`, tham số thứ hai là **phương sai**, nên độ lệch chuẩn là `σ = √σ²`.

---

# MỤC 1. XÁC SUẤT ĐẦY ĐỦ, BAYES, XÁC SUẤT CÓ ĐIỀU KIỆN

## Kiến thức nền cần nhớ

### 1. Công thức xác suất đầy đủ

Khi một kết quả có thể đến từ nhiều nguồn khác nhau, ta chia bài toán theo các nguồn đó.

Nếu `H1, H2, ..., Hn` là các nguồn có thể xảy ra và loại trừ nhau, thì:

```math
P(A)=P(H_1)P(A|H_1)+P(H_2)P(A|H_2)+...+P(H_n)P(A|H_n)
```

Hiểu đơn giản:  
**Xác suất xảy ra A = tổng xác suất đi qua từng nhánh để tạo ra A.**

### 2. Công thức Bayes

Khi đề có cụm **“biết rằng A đã xảy ra”**, và hỏi khả năng A đến từ nguồn nào, dùng Bayes:

```math
P(H_i|A)=\frac{P(H_i)P(A|H_i)}{P(A)}
```

Trong đó:

- Mẫu số `P(A)` là xác suất của dữ kiện đã biết.
- Tử số là xác suất đi đúng nhánh `Hi` và tạo ra `A`.

---

## Bài 1.1. Dây chuyền sản xuất

### Đề bài

Nhà máy có 3 dây chuyền A, B, C sản xuất lần lượt 40%, 35%, 25% sản phẩm. Tỷ lệ lỗi tương ứng là 3%, 5%, 8%.

Yêu cầu:

a. Tính xác suất chọn được sản phẩm lỗi.  
b. Biết sản phẩm bị lỗi, tính xác suất sản phẩm đó do dây chuyền C sản xuất.

### Nhận diện dạng bài

Sản phẩm lỗi có thể đến từ 3 nguồn: dây chuyền A, B hoặc C. Vì vậy câu a dùng **xác suất đầy đủ**. Câu b có cụm “biết sản phẩm bị lỗi”, nên dùng **Bayes**.

### Lời giải

Gọi `L` là biến cố “sản phẩm bị lỗi”.

Ta có:

```math
P(A)=0.40,\quad P(B)=0.35,\quad P(C)=0.25
```

```math
P(L|A)=0.03,\quad P(L|B)=0.05,\quad P(L|C)=0.08
```

#### a. Tính xác suất sản phẩm bị lỗi

Áp dụng công thức xác suất đầy đủ:

```math
P(L)=P(A)P(L|A)+P(B)P(L|B)+P(C)P(L|C)
```

Thay số:

```math
P(L)=0.40\cdot0.03+0.35\cdot0.05+0.25\cdot0.08
```

```math
P(L)=0.012+0.0175+0.020=0.0495
```

Vậy xác suất lấy được sản phẩm lỗi là `0.0495`, tức khoảng `4.95%`.

#### b. Biết sản phẩm bị lỗi, xác suất do dây chuyền C

Cần tính:

```math
P(C|L)
```

Theo Bayes:

```math
P(C|L)=\frac{P(C)P(L|C)}{P(L)}
```

Thay số:

```math
P(C|L)=\frac{0.25\cdot0.08}{0.0495}=\frac{0.020}{0.0495}=0.4040
```

### Kết luận

- a. `P(L)=0.0495`.
- b. `P(C|L)=0.4040`.

Ý nghĩa: nếu đã biết sản phẩm bị lỗi thì khả năng nó đến từ dây chuyền C khoảng `40.40%`.

---

## Bài 1.2. Chọn hộp rồi rút bi

### Đề bài

Có 3 hộp I, II, III được chọn với xác suất lần lượt 0.30, 0.50, 0.20. Tỷ lệ bi đỏ trong các hộp lần lượt là 70%, 40%, 20%.

Yêu cầu:

a. Tính xác suất rút được bi đỏ.  
b. Biết đã rút được bi đỏ, tính xác suất bi đến từ hộp I.

### Nhận diện dạng bài

Muốn rút được bi đỏ, trước hết phải chọn một hộp. Có 3 nhánh: chọn hộp I, II, III. Vì vậy câu a dùng xác suất đầy đủ. Câu b hỏi ngược lại: đã thấy bi đỏ, hỏi nguồn là hộp I, nên dùng Bayes.

### Lời giải

Gọi `Đ` là biến cố rút được bi đỏ.

```math
P(I)=0.30,\quad P(II)=0.50,\quad P(III)=0.20
```

```math
P(Đ|I)=0.70,\quad P(Đ|II)=0.40,\quad P(Đ|III)=0.20
```

#### a. Xác suất rút được bi đỏ

```math
P(Đ)=0.30\cdot0.70+0.50\cdot0.40+0.20\cdot0.20
```

```math
P(Đ)=0.21+0.20+0.04=0.45
```

#### b. Biết rút được bi đỏ, xác suất chọn hộp I

```math
P(I|Đ)=\frac{P(I)P(Đ|I)}{P(Đ)}
```

```math
P(I|Đ)=\frac{0.30\cdot0.70}{0.45}=\frac{0.21}{0.45}=0.4667
```

### Kết luận

- a. `P(Đ)=0.4500`.
- b. `P(I|Đ)=0.4667`.

---

## Bài 1.3. Xét nghiệm bệnh

### Nhận diện dạng bài

Đây là bài Bayes kinh điển. Có 2 nhóm người: mắc bệnh và không mắc bệnh. Kết quả dương tính có thể do mắc bệnh thật hoặc do dương tính giả.

Gọi:

- `B`: người đó mắc bệnh.
- `K`: người đó không mắc bệnh.
- `+`: xét nghiệm dương tính.

Ta có:

```math
P(B)=0.01,\quad P(K)=0.99
```

```math
P(+|B)=0.95,\quad P(+|K)=0.04
```

### a. Xác suất xét nghiệm dương tính

```math
P(+)=P(B)P(+|B)+P(K)P(+|K)
```

```math
P(+)=0.01\cdot0.95+0.99\cdot0.04=0.0095+0.0396=0.0491
```

### b. Biết dương tính, xác suất thật sự mắc bệnh

```math
P(B|+)=\frac{P(B)P(+|B)}{P(+)}
```

```math
P(B|+)=\frac{0.01\cdot0.95}{0.0491}=0.1935
```

### Vì sao kết quả không cao dù test chính xác 95%?

Vì bệnh rất hiếm, chỉ 1% dân số mắc bệnh. Trong nhóm 99% không mắc bệnh, vẫn có 4% bị dương tính giả. Số người dương tính giả có thể lớn hơn số người dương tính thật.

### Kết luận

- a. `P(+)=0.0491`.
- b. `P(B|+)=0.1935`.

---

## Bài 1.4. Hai xạ thủ

Gọi:

- `A`: xạ thủ A bắn trúng.
- `B`: xạ thủ B bắn trúng.

```math
P(A)=0.75,\quad P(B)=0.60
```

Vì hai xạ thủ bắn độc lập nên xác suất giao bằng tích xác suất.

### a. Cả hai cùng trúng

```math
P(A\cap B)=P(A)P(B)=0.75\cdot0.60=0.45
```

### b. Biết chỉ có đúng 1 viên trúng, xác suất viên trúng là của A

“Đúng 1 viên trúng” gồm 2 trường hợp:

1. A trúng, B trật.
2. A trật, B trúng.

```math
P(\text{đúng 1 trúng})=0.75\cdot0.40+0.25\cdot0.60=0.30+0.15=0.45
```

Trường hợp cần hỏi là “A trúng, B trật”:

```math
P(A\text{ trúng, B trật})=0.75\cdot0.40=0.30
```

Vậy:

```math
P(A\text{ trúng}|\text{đúng 1 trúng})=\frac{0.30}{0.45}=0.6667
```

### Kết luận

- a. `0.4500`.
- b. `0.6667`.

---

## Bài 1.5. Rút bài

Bộ bài có 52 lá, trong đó có 4 lá Ách và 48 lá không phải Ách. Rút 5 lá cùng lúc nên không xét thứ tự, dùng tổ hợp.

Tổng số cách rút 5 lá:

```math
C_{52}^{5}
```

### a. Xác suất có ít nhất 1 lá Ách

“Ít nhất 1 Ách” gồm 1, 2, 3, 4 Ách. Nếu cộng trực tiếp sẽ dài. Dùng biến cố đối nhanh hơn.

Biến cố đối của “ít nhất 1 Ách” là “không có lá Ách nào”.

```math
P(\text{ít nhất 1 Ách})=1-P(\text{không có Ách})
```

Số cách rút 5 lá không Ách là:

```math
C_{48}^{5}
```

Vậy:

```math
P=1-\frac{C_{48}^{5}}{C_{52}^{5}}=0.3412
```

### b. Xác suất có đúng 2 lá Ách

Muốn có đúng 2 Ách:

- Chọn 2 lá từ 4 lá Ách: `C(4,2)`.
- Chọn 3 lá còn lại từ 48 lá không Ách: `C(48,3)`.

```math
P=\frac{C_4^2C_{48}^3}{C_{52}^5}=0.0399
```

### Kết luận

- a. `0.3412`.
- b. `0.0399`.

---

## Bài 1.6. Rút bi cùng lúc

Hộp có 8 bi xanh, 12 bi đỏ, tổng 20 bi. Lấy cùng lúc 4 bi nên dùng tổ hợp.

Tổng số cách lấy:

```math
C_{20}^{4}
```

### a. Đúng 2 bi xanh

Muốn đúng 2 xanh thì 2 viên còn lại phải là đỏ.

```math
P=\frac{C_8^2C_{12}^2}{C_{20}^4}=0.3814
```

### b. Ít nhất 2 bi xanh

Ít nhất 2 xanh gồm các trường hợp:

- 2 xanh, 2 đỏ.
- 3 xanh, 1 đỏ.
- 4 xanh, 0 đỏ.

```math
P=\frac{C_8^2C_{12}^2+C_8^3C_{12}^1+C_8^4}{C_{20}^{4}}=0.4696
```

### Kết luận

- a. `0.3814`.
- b. `0.4696`.

---

## Bài 1.7. Sinh viên đậu môn X

Có 3 nhóm sinh viên: năm nhất, năm hai, năm ba. Sinh viên đậu có thể đến từ 1 trong 3 nhóm nên dùng xác suất đầy đủ.

Gọi `D` là biến cố sinh viên đậu môn X.

```math
P(D)=0.25\cdot0.80+0.45\cdot0.60+0.30\cdot0.30
```

```math
P(D)=0.20+0.27+0.09=0.56
```

Biết sinh viên đã đậu, xác suất thuộc năm hai:

```math
P(\text{năm hai}|D)=\frac{0.45\cdot0.60}{0.56}=0.4821
```

### Kết luận

- a. `0.5600`.
- b. `0.4821`.

---

## Bài 1.8. Chuyển bi giữa hai hộp

Bài này phải chia theo màu viên bi được chuyển từ hộp A sang hộp B.

Hộp A: 5 đỏ, 3 xanh. Tổng 8 bi.  
Hộp B ban đầu: 4 đỏ, 6 xanh. Tổng 10 bi.

### a. Xác suất rút ở B được bi đỏ

Có 2 trường hợp:

#### Trường hợp 1: Chuyển bi đỏ từ A sang B

```math
P(\text{chuyển đỏ})=\frac58
```

Khi đó hộp B có 5 đỏ, 6 xanh, tổng 11 bi. Xác suất rút đỏ từ B:

```math
\frac5{11}
```

Xác suất nhánh này:

```math
\frac58\cdot\frac5{11}
```

#### Trường hợp 2: Chuyển bi xanh từ A sang B

```math
P(\text{chuyển xanh})=\frac38
```

Khi đó hộp B có 4 đỏ, 7 xanh, tổng 11 bi. Xác suất rút đỏ từ B:

```math
\frac4{11}
```

Xác suất nhánh này:

```math
\frac38\cdot\frac4{11}
```

Cộng hai nhánh:

```math
P(Đ_B)=\frac58\cdot\frac5{11}+\frac38\cdot\frac4{11}=0.4205
```

### b. Biết rút ở B được đỏ, xác suất viên chuyển là xanh

Đây là Bayes. Tử số là nhánh “chuyển xanh rồi rút đỏ”. Mẫu số là xác suất rút đỏ ở B đã tính ở câu a.

```math
P(\text{chuyển xanh}|Đ_B)=\frac{\frac38\cdot\frac4{11}}{0.4205}=0.3243
```

### Kết luận

- a. `0.4205`.
- b. `0.3243`.

---

## Bài 1.9. Tỷ lệ mắc bệnh theo giới tính

Gọi `M` là biến cố mắc bệnh.

Có 2 nhóm: nữ và nam.

```math
P(\text{nữ})=0.55,\quad P(\text{nam})=0.45
```

```math
P(M|\text{nữ})=0.20,\quad P(M|\text{nam})=0.10
```

### a. Xác suất mắc bệnh

```math
P(M)=0.55\cdot0.20+0.45\cdot0.10=0.11+0.045=0.155
```

### b. Biết mắc bệnh, xác suất là nam

```math
P(\text{nam}|M)=\frac{0.45\cdot0.10}{0.155}=0.2903
```

### Kết luận

- a. `0.1550`.
- b. `0.2903`.

---

## Bài 1.10. Tung xu rồi rút bi

Có 2 trường hợp theo kết quả tung xu.

- Sấp: xác suất `1/2`, bình có 1 đỏ và 2 vàng, nên xác suất rút đỏ là `1/3`.
- Ngửa: xác suất `1/2`, bình có 2 đỏ và 2 vàng, nên xác suất rút đỏ là `2/4`.

### a. Xác suất rút được bi đỏ

```math
P(Đ)=\frac12\cdot\frac13+\frac12\cdot\frac24
```

```math
P(Đ)=0.1667+0.25=0.4167
```

### b. Biết rút được đỏ, xác suất đồng xu ra ngửa

Tử số là nhánh “ngửa rồi rút đỏ”:

```math
\frac12\cdot\frac24=0.25
```

Mẫu số là xác suất rút đỏ:

```math
P(Đ)=0.4167
```

```math
P(\text{ngửa}|Đ)=\frac{0.25}{0.4167}=0.6000
```

### Kết luận

- a. `0.4167`.
- b. `0.6000`.

---

# MỤC 2. PHÂN PHỐI CHUẨN

## Kiến thức nền cần nhớ

Nếu:

```math
X\sim N(\mu,\sigma^2)
```

thì chuẩn hóa:

```math
Z=\frac{X-\mu}{\sigma}
```

với `Z ~ N(0,1)`.

Khi tính xác suất khoảng:

```math
P(a<X<b)=\Phi\left(\frac{b-\mu}{\sigma}\right)-\Phi\left(\frac{a-\mu}{\sigma}\right)
```

Khi tìm `T`:

- Nếu `P(X<T)=p`, tìm `z_p` sao cho `Φ(z_p)=p`, rồi `T=μ+σz_p`.
- Nếu `P(X>T)=p`, đổi thành `P(X<T)=1-p`.

## Bảng lời giải chi tiết rút gọn

| Bài | Phân phối | σ | Câu a | Câu b |
|---:|---|---:|---|---|
| 2.1 | `N(60,64)` | 8 | `P(50<X<70)=Φ(1.25)-Φ(-1.25)=0.7887` | `T=60+8×1.2816=70.2524` |
| 2.2 | `N(100,225)` | 15 | `P=Φ(1.3333)-Φ(-1)=0.7501` | `T=100+15×1.6449=124.6728` |
| 2.3 | `N(500,1600)` | 40 | `P=Φ(1.5)-Φ(-1.25)=0.8275` | `T=500+40×(-1.2816)=448.7379` |
| 2.4 | `N(170,36)` | 6 | `P=Φ(1.6667)-Φ(-1.6667)=0.9044` | `P(X>T)=0.80 ⇒ P(X<T)=0.20`; `T=170+6×(-0.8416)=164.9503` |
| 2.5 | `N(30,16)` | 4 | `P=Φ(1.25)-Φ(-1.25)=0.7887` | `P(X>T)=0.05 ⇒ P(X<T)=0.95`; `T=30+4×1.6449=36.5794` |
| 2.6 | `N(75,100)` | 10 | `P=Φ(1.5)-Φ(-1)=0.7745` | `T=75+10×1.96=94.5996` |
| 2.7 | `N(12,6.25)` | 2.5 | `P=Φ(1.2)-Φ(-1.2)=0.7699` | `T=12+2.5×(-0.8416)=9.8960` |
| 2.8 | `N(200,625)` | 25 | `P=Φ(1.2)-Φ(-0.8)=0.6731` | `P(X>T)=0.85 ⇒ P(X<T)=0.15`; `T=200+25×(-1.0364)=174.0908` |
| 2.9 | `N(3.5,0.16)` | 0.4 | `P=Φ(1.5)-Φ(-1.25)=0.8275` | `T=3.5+0.4×2.3263=4.4305` |
| 2.10 | `N(1000,14400)` | 120 | `P=Φ(0.8333)-Φ(-1.25)=0.6915` | `P(X>T)=0.15 ⇒ P(X<T)=0.85`; `T=1000+120×1.0364=1124.3700` |

### Vì sao phải chuẩn hóa?

Bảng phân phối chuẩn thường chỉ có chuẩn tắc `N(0,1)`. Đề lại cho `X` có trung bình và độ lệch chuẩn riêng, nên ta đổi `X` về `Z`. Sau khi đổi, có thể tra bảng hoặc dùng máy tính để lấy `Φ(z)`.

---

# MỤC 3. BIẾN NGẪU NHIÊN LIÊN TỤC 1 BIẾN

## Kiến thức nền cần nhớ

Một hàm `f(x)` là mật độ xác suất nếu:

1. `f(x) ≥ 0` trên miền xác định.
2. Tổng diện tích dưới đồ thị bằng 1:

```math
\int_{-\infty}^{+\infty}f(x)dx=1
```

Vì đề thường cho `f(x)=kg(x)`, ta tìm `k` bằng:

```math
\int_a^b kg(x)dx=1
```

Sau khi có `k`:

```math
E(X)=\int_a^b xf(x)dx
```

```math
E(X^2)=\int_a^b x^2f(x)dx
```

```math
Var(X)=E(X^2)-[E(X)]^2
```

```math
P(c<X<d)=\int_c^d f(x)dx
```

## Bài 3.1

```math
f(x)=kx,\quad 0<x<2
```

### Tìm k

Vì tổng xác suất bằng 1:

```math
\int_0^2kx\,dx=1
```

```math
k\left[\frac{x^2}{2}\right]_0^2=1
```

```math
k\cdot2=1\Rightarrow k=0.5
```

### Tính kỳ vọng

```math
E(X)=\int_0^2x\cdot0.5x\,dx=0.5\int_0^2x^2dx
```

```math
E(X)=0.5\left[\frac{x^3}{3}\right]_0^2=\frac43=1.3333
```

### Tính phương sai

```math
E(X^2)=\int_0^2x^2\cdot0.5x\,dx=0.5\int_0^2x^3dx=2
```

```math
Var(X)=2-\left(\frac43\right)^2=\frac29=0.2222
```

### Tính xác suất

```math
P(0.5<X<1.5)=\int_{0.5}^{1.5}0.5x\,dx=0.5
```

Kết quả: `k=0.5`, `E(X)=1.3333`, `Var(X)=0.2222`, xác suất `0.5000`.

## Bảng kết quả các bài 3.2 đến 3.10

Các bài còn lại làm y hệt quy trình bài 3.1: tìm `k`, rồi tính `E(X)`, `E(X²)`, `Var(X)`, cuối cùng tính xác suất theo cận đề bài.

| Bài | Hàm mật độ | k | E(X) | Var(X) | Xác suất cần tìm |
|---:|---|---:|---:|---:|---:|
| 3.2 | `kx², 0<x<3` | 0.1111 | 2.2500 | 0.3375 | 0.2593 |
| 3.3 | `k(x+1), 0<x<2` | 0.2500 | 1.1667 | 0.3056 | 0.5000 |
| 3.4 | `k(4-x), 0<x<4` | 0.1250 | 1.3333 | 0.8889 | 0.5000 |
| 3.5 | `k/x², 1<x<3` | 1.5000 | 1.6479 | 0.2827 | 0.4000 |
| 3.6 | `ksin(x), 0<x<π` | 0.5000 | 1.5708 | 0.4674 | 0.4330 |
| 3.7 | `k(1-x²), -1<x<1` | 0.7500 | 0.0000 | 0.2000 | 0.6875 |
| 3.8 | `k(2x+1), 0<x<1` | 0.5000 | 0.5833 | 0.0764 | 0.5000 |
| 3.9 | `ke^(-x/2), x>0` | 0.5000 | 2.0000 | 4.0000 | 0.4712 |
| 3.10 | `kxe^(-x), x>0` | 1.0000 | 2.0000 | 2.0000 | 0.5768 |

### Giải thích vì sao bài 3.7 có E(X)=0

Ở bài 3.7, miền là `(-1,1)` đối xứng qua 0 và hàm mật độ `k(1-x²)` cũng đối xứng. Khi đó phần bên trái và bên phải cân bằng nhau, nên trung bình lý thuyết nằm đúng tại 0. Vì vậy `E(X)=0`.

---

# MỤC 4. ƯỚC LƯỢNG VÀ KIỂM ĐỊNH

## Kiến thức nền cần nhớ

### 1. Ước lượng điểm

- Với kỳ vọng tổng thể `μ`, ước lượng điểm là trung bình mẫu `x̄`.
- Với tỷ lệ tổng thể `p`, ước lượng điểm là:

```math
\hat p=\frac{x}{n}
```

### 2. Khoảng tin cậy cho kỳ vọng

```math
\bar x\pm z_{\alpha/2}\frac{s}{\sqrt n}
```

Ý nghĩa: ta lấy trung bình mẫu rồi cộng/trừ một sai số.

### 3. Khoảng tin cậy cho tỷ lệ

```math
\hat p\pm z_{\alpha/2}\sqrt{\frac{\hat p(1-\hat p)}{n}}
```

### 4. Cỡ mẫu

Kỳ vọng:

```math
n\ge\left(\frac{zs}{d}\right)^2
```

Tỷ lệ:

```math
n\ge\frac{z^2\hat p(1-\hat p)}{d^2}
```

### 5. Kiểm định

Tính thống kê kiểm định `Z`, sau đó so với ngưỡng tới hạn.

Mức ý nghĩa 5%:

- Kiểm định phải: bác bỏ nếu `Z > 1.645`.
- Kiểm định trái: bác bỏ nếu `Z < -1.645`.
- Kiểm định hai phía: bác bỏ nếu `|Z| > 1.96`.

## Bài 4.1

Dữ kiện: `n=64`, `x̄=168.5`, `s=7.2`.

### a. Ước lượng điểm

Ước lượng điểm cho `μ` là:

```math
\bar x=168.5
```

### b. Khoảng tin cậy 95%

Với 95%, `z=1.96`.

Sai số:

```math
E=1.96\cdot\frac{7.2}{\sqrt{64}}=1.764
```

Khoảng tin cậy:

```math
168.5\pm1.764=[166.736;170.264]
```

### c. Cỡ mẫu với d=1.5

```math
n\ge\left(\frac{1.96\cdot7.2}{1.5}\right)^2=88.47
```

Làm tròn lên: `n=89`.

### d. Kiểm định

```math
H_0:\mu=170,\quad H_1:\mu<170
```

Thống kê kiểm định:

```math
Z=\frac{168.5-170}{7.2/\sqrt{64}}=-1.6667
```

Vì kiểm định trái mức 5%, ngưỡng là `-1.645`. Ta có:

```math
-1.6667<-1.645
```

nên bác bỏ `H0`.

Kết luận: ở mức ý nghĩa 5%, có đủ cơ sở để cho rằng chiều cao trung bình nhỏ hơn 170.

## Bảng kết quả và kết luận các bài 4.2 đến 4.10

| Bài | Dạng | Ước lượng điểm | Khoảng tin cậy | Cỡ mẫu | Kiểm định |
|---:|---|---:|---|---:|---|
| 4.2 | Kỳ vọng | 12.4 | `[11.4984; 13.3016]` | 46 | `Z=-1.7143`; hai phía 5%, `|Z|<1.96`, không bác bỏ H0 |
| 4.3 | Kỳ vọng | 7.1 | `[6.8862; 7.3139]` | 74 | `Z=0.7692`; kiểm định phải, không bác bỏ H0 |
| 4.4 | Kỳ vọng | 50.8 | `[49.5400; 52.0600]` | 78 | `Z=-1.8667`; kiểm định trái, bác bỏ H0 |
| 4.5 | Kỳ vọng | 9.6 | `[9.1348; 10.0652]` | 71 | `Z=2.0000`; kiểm định phải, bác bỏ H0 |
| 4.6 | Tỷ lệ | 0.1300 | `[0.0970; 0.1630]` | 483 | `Z=2.0000`; kiểm định phải, bác bỏ H0 |
| 4.7 | Tỷ lệ | 0.1200 | `[0.0865; 0.1535]` | 1121 | `Z=-2.1004`; kiểm định trái, bác bỏ H0 |
| 4.8 | Tỷ lệ | 0.4600 | `[0.4127; 0.5073]` | 269 | `Z=-1.3856`; hai phía, không bác bỏ H0 |
| 4.9 | Tỷ lệ | 0.2400 | `[0.2135; 0.2665]` | 1752 | `Z=3.1623`; kiểm định phải, bác bỏ H0 |
| 4.10 | Tỷ lệ | 0.1200 | `[0.0722; 0.1678]` | 358 | `Z=1.0541`; hai phía, không bác bỏ H0 |

### Cách đọc bảng kiểm định

Ví dụ bài 4.4 có `Z=-1.8667`. Vì đối thuyết là `μ<52`, đây là kiểm định trái. Ngưỡng bác bỏ ở mức 5% là `-1.645`. Do `-1.8667<-1.645`, ta bác bỏ `H0`.

---

# MỤC 5. TƯƠNG QUAN VÀ HỒI QUY TUYẾN TÍNH

## Kiến thức nền cần nhớ

### 1. Hệ số tương quan r

`r` cho biết X và Y có quan hệ tuyến tính mạnh hay yếu.

- `r > 0`: tương quan thuận, X tăng thì Y có xu hướng tăng.
- `r < 0`: tương quan nghịch, X tăng thì Y có xu hướng giảm.
- `|r|` càng gần 1 thì quan hệ tuyến tính càng mạnh.

### 2. Hồi quy tuyến tính Y theo X

Phương trình hồi quy có dạng:

```math
\hat Y=a+bX
```

Trong đó:

- `b` là hệ số góc. X tăng 1 đơn vị thì Y trung bình thay đổi khoảng `b` đơn vị.
- `a` là hệ số chặn, giá trị dự đoán của Y khi X bằng 0.

### 3. Dự đoán

Muốn dự đoán tại `X=x0`, thay `x0` vào:

```math
\hat Y=a+bx_0
```

## Bài 5.1. Quảng cáo và doanh thu

Dữ liệu:

| X | Y |
|---:|---:|
| 2 | 20 |
| 3 | 25 |
| 5 | 37 |
| 6 | 42 |
| 8 | 55 |
| 9 | 60 |

Kết quả tính được:

```math
r=0.9982
```

Vì `r` dương và rất gần 1, X và Y có tương quan thuận rất mạnh. Nghĩa là chi phí quảng cáo tăng thì doanh thu có xu hướng tăng rõ rệt.

Phương trình hồi quy:

```math
\hat Y=8.8571+5.6429X
```

Dự đoán khi `X=7`:

```math
\hat Y=8.8571+5.6429\cdot7=48.3571
```

Kết luận: khi chi phí quảng cáo là 7 triệu, doanh thu dự đoán khoảng `48.3571` triệu.

## Bảng kết quả bài 5.2 đến 5.10

| Bài | r | Nhận xét | Phương trình hồi quy | Dự đoán |
|---:|---:|---|---|---:|
| 5.2 | 0.9983 | Thuận rất mạnh | `Ŷ = 3.5714 + 0.6929X` | `Y(8)=9.1143` |
| 5.3 | 0.9894 | Thuận rất mạnh | `Ŷ = -2.8571 + 5.9143X` | `Y(27)=156.8286` |
| 5.4 | 0.9912 | Thuận rất mạnh | `Ŷ = 1.8667 + 2.8857X` | `Y(7)=22.0667` |
| 5.5 | -0.9920 | Nghịch rất mạnh | `Ŷ = 147.3333 - 4.7000X` | `Y(15)=76.8333` |
| 5.6 | 0.9991 | Thuận rất mạnh | `Ŷ = 4.5513 + 6.6923X` | `Y(11)=78.1667` |
| 5.7 | 0.9892 | Thuận rất mạnh | `Ŷ = -3.0629 + 0.1646X` | `Y(48)=4.8371` |
| 5.8 | 0.9994 | Thuận rất mạnh | `Ŷ = 3.6667 + 4.5333X` | `Y(7)=35.4000` |
| 5.9 | 0.9949 | Thuận rất mạnh | `Ŷ = -1.0667 + 1.6464X` | `Y(10)=15.3970` |
| 5.10 | 0.9977 | Thuận rất mạnh | `Ŷ = 6.1872 + 2.3498X` | `Y(7)=22.6355` |

### Cách diễn giải kết quả hồi quy

Ví dụ bài 5.5:

```math
\hat Y=147.3333-4.7X
```

Hệ số `b=-4.7` âm, nghĩa là giá bán tăng 1 đơn vị thì số lượng bán dự đoán giảm trung bình khoảng 4.7 đơn vị. Điều này hợp lý vì giá càng cao thì nhu cầu mua thường giảm.

---

# CHECKLIST HỌC LẠI TỪ MẤT GỐC

1. Gặp bài nhiều nguồn → vẽ cây xác suất.
2. Gặp “biết rằng” → nghĩ ngay đến xác suất có điều kiện hoặc Bayes.
3. Gặp “rút cùng lúc/chọn” → dùng tổ hợp.
4. Gặp `N(μ,σ²)` → lấy căn phương sai để ra `σ`.
5. Gặp hàm mật độ → tích phân bằng 1 để tìm `k` trước.
6. Gặp khoảng tin cậy → ước lượng điểm ± sai số.
7. Gặp kiểm định → ghi `H0`, `H1`, tính `Z`, so ngưỡng, kết luận bằng lời.
8. Gặp hồi quy → tính `r`, lập `Y=a+bX`, thay X để dự đoán.
