# HƯỚNG DẪN BẤM MÁY TÍNH CASIO FX-570 CHO 50 BÀI XSTK

Áp dụng cho bộ 50 bài đã tạo gồm: xác suất chương 1, phân phối chuẩn, BNN liên tục 1 biến, ước lượng - kiểm định, tương quan - hồi quy.

> Dòng máy tham chiếu: Casio fx-570VN PLUS / fx-570ES PLUS. Nếu máy của bạn khác giao diện, giữ nguyên logic bấm: tính tổ hợp `nCr`, chuẩn hóa `Z`, dùng `DIST` nếu có, dùng `STAT` cho thống kê và hồi quy.

---

## 0. Quy ước bấm nhanh

### 0.1. Reset máy khi số liệu bị rối

```text
SHIFT → 9(CLR) → 3(All) → = → AC
```

### 0.2. Tính tổ hợp C(n,k)

Dùng khi gặp rút bài, rút bi, chọn mẫu không hoàn lại.

```text
n → SHIFT → ÷(nCr) → k → =
```

Ví dụ: `C(52,5)`

```text
52 → SHIFT → ÷(nCr) → 5 → =
```

### 0.3. Lũy thừa

```text
a^b:  a → x^□ → b → =
```

### 0.4. Nhập phân số

```text
a/b:  a → a b/c → b → =
```

Hoặc dùng dấu chia `/` bình thường.

### 0.5. Làm tròn

Sau khi ra kết quả, bài này thống nhất làm tròn 4 chữ số thập phân nếu đề không yêu cầu khác.

---

# MỤC 1. XÁC SUẤT ĐẦY ĐỦ, BAYES, TỔ HỢP

## Công thức nhận diện nhanh

### Xác suất đầy đủ

Khi đề có nhiều nguồn/nhóm/hộp/dây chuyền:

$$P(A)=\sum_i P(H_i)P(A|H_i)$$

Bấm máy: nhập thẳng tổng các tích.

```text
P(H1)×P(A|H1)+P(H2)×P(A|H2)+...=
```

### Bayes

Khi đề hỏi “biết rằng đã xảy ra A, xác suất thuộc nhóm Hi là bao nhiêu?”:

$$P(H_i|A)=\frac{P(H_i)P(A|H_i)}{P(A)}$$

Bấm máy:

```text
(P(Hi)×P(A|Hi)) ÷ P(A) =
```

### Tổ hợp rút không hoàn lại

$$P=\frac{\text{số cách thuận lợi}}{\text{số cách tất cả}}$$

Dùng `nCr`.

---

## Bài 1.1

Dạng: xác suất đầy đủ + Bayes.

### a/ Xác suất lỗi

```text
0.4×0.03+0.35×0.05+0.25×0.08=
```

Kết quả: `0.0495`.

### b/ Biết lỗi, xác suất do C

```text
(0.25×0.08)÷0.0495=
```

Kết quả: `0.4040`.

Mẹo: mẫu số Bayes chính là kết quả câu a/.

---

## Bài 1.2

Dạng: chọn hộp rồi rút bi.

### a/ Xác suất rút đỏ

```text
0.30×0.70+0.50×0.40+0.20×0.20=
```

Kết quả: `0.4500`.

### b/ Biết đỏ, xác suất từ hộp I

```text
(0.30×0.70)÷0.45=
```

Kết quả: `0.4667`.

---

## Bài 1.3

Dạng: xét nghiệm bệnh, chú ý dương tính giả.

### a/ Xác suất dương tính

```text
0.01×0.95+0.99×0.04=
```

Kết quả: `0.0491`.

### b/ Dương tính rồi, xác suất thật mắc bệnh

```text
(0.01×0.95)÷0.0491=
```

Kết quả: `0.1935`.

Mẹo nhanh: bệnh hiếm thì dù test tốt, xác suất thật mắc sau dương tính vẫn có thể không cao.

---

## Bài 1.4

Dạng: hai biến cố độc lập + xác suất có điều kiện.

### a/ Cả A và B cùng trúng

```text
0.75×0.60=
```

Kết quả: `0.4500`.

### b/ Biết đúng 1 viên trúng, xác suất viên trúng là của A

Mẫu số “đúng 1 trúng”:

```text
0.75×0.40+0.25×0.60=
```

Ra `0.45`.

Tử số “A trúng, B trật”:

```text
0.75×0.40=
```

Ra `0.30`.

Xác suất cần tìm:

```text
0.30÷0.45=
```

Kết quả: `0.6667`.

---

## Bài 1.5

Dạng: bộ bài 52 lá, dùng `nCr`.

### a/ Ít nhất 1 Ách

Dùng biến cố đối: không có Ách.

```text
1-(48 nCr 5)÷(52 nCr 5)=
```

Bấm cụ thể:

```text
1 - (48 SHIFT ÷ 5) ÷ (52 SHIFT ÷ 5) =
```

Kết quả: `0.3412`.

### b/ Đúng 2 Ách

```text
(4 nCr 2)×(48 nCr 3)÷(52 nCr 5)=
```

Kết quả: `0.0399`.

Mẹo: “ít nhất 1” thường dùng `1 - không có` để bấm nhanh.

---

## Bài 1.6

Dạng: rút 4 bi từ 8 xanh, 12 đỏ.

### a/ Đúng 2 xanh

```text
(8 nCr 2)×(12 nCr 2)÷(20 nCr 4)=
```

Kết quả: `0.3814`.

### b/ Ít nhất 2 xanh

Cách bấm nhanh:

```text
[(8 nCr 2)(12 nCr 2)+(8 nCr 3)(12 nCr 1)+(8 nCr 4)]÷(20 nCr 4)=
```

Kết quả: `0.4696`.

Mẹo: “ít nhất 2 xanh” gồm 2 xanh, 3 xanh, 4 xanh.

---

## Bài 1.7

Dạng: xác suất đầy đủ + Bayes theo nhóm sinh viên.

### a/ Xác suất đậu

```text
0.25×0.80+0.45×0.60+0.30×0.30=
```

Kết quả: `0.5600`.

### b/ Biết đậu, xác suất thuộc năm hai

```text
(0.45×0.60)÷0.56=
```

Kết quả: `0.4821`.

---

## Bài 1.8

Dạng: chuyển bi giữa 2 hộp, dùng cây xác suất.

### a/ Xác suất rút ở B được đỏ

Nếu chuyển đỏ từ A: xác suất `5/8`, B thành 5 đỏ 6 xanh, rút đỏ `5/11`.

Nếu chuyển xanh từ A: xác suất `3/8`, B thành 4 đỏ 7 xanh, rút đỏ `4/11`.

Bấm:

```text
(5÷8)×(5÷11)+(3÷8)×(4÷11)=
```

Kết quả: `0.4205`.

### b/ Biết rút đỏ ở B, xác suất bi chuyển là xanh

```text
[(3÷8)×(4÷11)]÷0.4205=
```

Kết quả: `0.3243`.

---

## Bài 1.9

Dạng: xác suất đầy đủ + Bayes theo giới tính.

### a/ Xác suất mắc bệnh

```text
0.55×0.20+0.45×0.10=
```

Kết quả: `0.1550`.

### b/ Biết mắc bệnh, xác suất là nam

```text
(0.45×0.10)÷0.155=
```

Kết quả: `0.2903`.

---

## Bài 1.10

Dạng: tung xu rồi rút bi.

### a/ Xác suất rút đỏ

Nếu sấp: đỏ `1/3`. Nếu ngửa: đỏ `2/4`.

```text
0.5×(1÷3)+0.5×(2÷4)=
```

Kết quả: `0.4167`.

### b/ Biết rút đỏ, xác suất xu ra ngửa

```text
[0.5×(2÷4)]÷0.4167=
```

Kết quả: `0.6000`.

---

# MỤC 2. PHÂN PHỐI CHUẨN

## Cách xử lý bằng fx-570

### Bước 1. Xác định đúng độ lệch chuẩn

Nếu đề ghi:

$$X\sim N(\mu,\sigma^2)$$

thì số thứ hai là phương sai, phải lấy căn:

```text
σ = √phương_sai
```

Ví dụ `N(60,64)` thì `σ=8`, không phải 64.

### Bước 2. Chuẩn hóa

$$Z=\frac{X-\mu}{\sigma}$$

### Bước 3. Tính xác suất

$$P(a<X<b)=\Phi\left(\frac{b-\mu}{\sigma}\right)-\Phi\left(\frac{a-\mu}{\sigma}\right)$$

### Nếu máy có DIST / Normal CD

Thử:

```text
MODE → DIST → Normal CD
Lower = a
Upper = b
σ = độ lệch chuẩn
μ = trung bình
=
```

Tìm T theo xác suất tích lũy:

```text
MODE → DIST → InvN
Area = xác suất bên trái
σ = độ lệch chuẩn
μ = trung bình
=
```

Nếu điều kiện là `P(X>T)=q`, đổi về bên trái:

```text
P(X<T)=1-q
```

### Nếu máy không có DIST

Dùng bảng chuẩn tắc hoặc app/bảng Z. Máy fx-570 vẫn hỗ trợ tính phần chuẩn hóa `Z=(x-μ)/σ` rất nhanh.

---

## Bảng bấm nhanh cho 10 bài chuẩn

| Bài | σ | Ý a/ bấm Normal CD | Ý b/ bấm InvN | Kết quả chính |
|---:|---:|---|---|---|
| 2.1 | 8 | Lower=50, Upper=70, σ=8, μ=60 | Area=0.90, σ=8, μ=60 | a≈0.7887; T≈70.2524 |
| 2.2 | 15 | Lower=85, Upper=120, σ=15, μ=100 | Area=0.95, σ=15, μ=100 | a≈0.7501; T≈124.6728 |
| 2.3 | 40 | Lower=450, Upper=560, σ=40, μ=500 | Area=0.10, σ=40, μ=500 | a≈0.8275; T≈448.7379 |
| 2.4 | 6 | Lower=160, Upper=180, σ=6, μ=170 | Area=0.20, σ=6, μ=170 | a≈0.9044; T≈164.9503 |
| 2.5 | 4 | Lower=25, Upper=35, σ=4, μ=30 | Area=0.95, σ=4, μ=30 | a≈0.7887; T≈36.5794 |
| 2.6 | 10 | Lower=65, Upper=90, σ=10, μ=75 | Area=0.975, σ=10, μ=75 | a≈0.7745; T≈94.5996 |
| 2.7 | 2.5 | Lower=9, Upper=15, σ=2.5, μ=12 | Area=0.20, σ=2.5, μ=12 | a≈0.7699; T≈9.8960 |
| 2.8 | 25 | Lower=180, Upper=230, σ=25, μ=200 | Area=0.15, σ=25, μ=200 | a≈0.6731; T≈174.0908 |
| 2.9 | 0.4 | Lower=3.0, Upper=4.1, σ=0.4, μ=3.5 | Area=0.99, σ=0.4, μ=3.5 | a≈0.8275; T≈4.4305 |
| 2.10 | 120 | Lower=850, Upper=1100, σ=120, μ=1000 | Area=0.85, σ=120, μ=1000 | a≈0.6915; T≈1124.3700 |

Mẹo cực nhanh:

- `P(X<T)=p` dùng `Area=p`.
- `P(X>T)=p` đổi thành `Area=1-p`.
- `P(a<X<b)` dùng Normal CD, không cần tự trừ bảng.

---

# MỤC 3. BNN LIÊN TỤC 1 BIẾN

## Công thức phải nhớ

Với mật độ `f(x)`:

$$\int f(x)dx=1$$

$$E(X)=\int x f(x)dx$$

$$E(X^2)=\int x^2 f(x)dx$$

$$Var(X)=E(X^2)-[E(X)]^2$$

$$P(a<X<b)=\int_a^b f(x)dx$$

## Bấm tích phân trên fx-570

Dùng phím tích phân:

```text
∫( biểu_thức_theo_X, cận_dưới, cận_trên )
```

Thường thao tác:

```text
SHIFT → ∫dx → nhập hàm → nhập cận dưới → nhập cận trên → =
```

Biến `X` nhập bằng:

```text
ALPHA → ) hoặc phím có chữ X tùy dòng máy
```

## Cách tìm k bằng máy

Nếu `f(x)=k g(x)` trên `(a,b)`:

$$k=\frac{1}{\int_a^b g(x)dx}$$

Bấm:

```text
1 ÷ ∫(g(X), a, b) =
```

Sau khi có `k`, gán vào A để dùng lại:

```text
k → SHIFT → RCL(STO) → A
```

Khi nhập biểu thức sau, dùng:

```text
ALPHA → A
```

---

## Bảng bấm nhanh cho 10 bài BNN liên tục 1 biến

| Bài | Tìm k | E(X) | Var(X) | Xác suất |
|---:|---|---|---|---|
| 3.1 | `1÷∫(X,0,2)` | `∫(X×A×X,0,2)` | `∫(X^2×A×X,0,2)-E^2` | `∫(A×X,0.5,1.5)` |
| 3.2 | `1÷∫(X^2,0,3)` | `∫(X×A×X^2,0,3)` | `∫(X^2×A×X^2,0,3)-E^2` | `∫(A×X^2,1,2)` |
| 3.3 | `1÷∫(X+1,0,2)` | `∫(X×A×(X+1),0,2)` | `∫(X^2×A×(X+1),0,2)-E^2` | `∫(A×(X+1),0.5,1.5)` |
| 3.4 | `1÷∫(4-X,0,4)` | `∫(X×A×(4-X),0,4)` | `∫(X^2×A×(4-X),0,4)-E^2` | `∫(A×(4-X),1,3)` |
| 3.5 | `1÷∫(1÷X^2,1,3)` | `∫(X×A÷X^2,1,3)` | `∫(X^2×A÷X^2,1,3)-E^2` | `∫(A÷X^2,1.5,2.5)` |
| 3.6 | `1÷∫(sin(X),0,π)` | `∫(X×A×sin(X),0,π)` | `∫(X^2×A×sin(X),0,π)-E^2` | `∫(A×sin(X),π÷6,π÷2)` |
| 3.7 | `1÷∫(1-X^2,-1,1)` | `∫(X×A×(1-X^2),-1,1)` | `∫(X^2×A×(1-X^2),-1,1)-E^2` | `∫(A×(1-X^2),-0.5,0.5)` |
| 3.8 | `1÷∫(2X+1,0,1)` | `∫(X×A×(2X+1),0,1)` | `∫(X^2×A×(2X+1),0,1)-E^2` | `∫(A×(2X+1),0.25,0.75)` |
| 3.9 | `1÷∫(e^(-X÷2),0,∞)` | `∫(X×A×e^(-X÷2),0,∞)` | `∫(X^2×A×e^(-X÷2),0,∞)-E^2` | `∫(A×e^(-X÷2),1,4)` |
| 3.10 | `1÷∫(X×e^(-X),0,∞)` | `∫(X×A×X×e^(-X),0,∞)` | `∫(X^2×A×X×e^(-X),0,∞)-E^2` | `∫(A×X×e^(-X),1,3)` |

Ghi chú với cận `∞`: nhiều máy fx-570 không nhập vô cực trực tiếp. Dùng cận lớn như `50` hoặc `100` cho hàm mũ giảm nhanh. Ví dụ bài 3.9, 3.10 có thể nhập cận trên `50` là đủ chính xác.

## Kết quả để kiểm tra nhanh

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

Mẹo: nếu hàm đối xứng chẵn trên `(-a,a)` như bài 3.7 thì `E(X)=0`, không cần bấm lâu.

---

# MỤC 4. ƯỚC LƯỢNG VÀ KIỂM ĐỊNH

## Công thức bấm nhanh

### 4.1. Khoảng tin cậy kỳ vọng

Với n đủ lớn:

$$\bar x \pm z_{\alpha/2}\frac{s}{\sqrt n}$$

Các mốc Z thường dùng:

| Độ tin cậy | z |
|---:|---:|
| 90% | 1.645 |
| 95% | 1.96 |
| 98% | 2.326 |
| 99% | 2.576 |

Bấm sai số:

```text
z × s ÷ √n =
```

### 4.2. Cỡ mẫu cho kỳ vọng

$$n \ge \left(\frac{z s}{d}\right)^2$$

Bấm:

```text
(z×s÷d)^2=
```

Sau đó làm tròn lên.

### 4.3. Kiểm định kỳ vọng

$$Z=\frac{\bar x-\mu_0}{s/\sqrt n}$$

Bấm:

```text
(xbar - mu0) ÷ (s ÷ √n) =
```

Quyết định nhanh:

- `H1: μ > μ0`: bác bỏ nếu `Z > 1.645` ở mức 5%.
- `H1: μ < μ0`: bác bỏ nếu `Z < -1.645` ở mức 5%.
- `H1: μ ≠ μ0`: bác bỏ nếu `|Z| > 1.96` ở mức 5%.

### 4.4. Khoảng tin cậy tỷ lệ

$$\hat p \pm z\sqrt{\frac{\hat p(1-\hat p)}{n}}$$

Bấm:

```text
x÷n = p_hat
z × √(p_hat×(1-p_hat)÷n)=
```

### 4.5. Cỡ mẫu cho tỷ lệ

Nếu chưa có ước lượng tốt, dùng `p=0.5` để an toàn:

$$n \ge \frac{z^2p(1-p)}{d^2}$$

Bấm:

```text
z^2×p×(1-p)÷d^2=
```

### 4.6. Kiểm định tỷ lệ

$$Z=\frac{\hat p-p_0}{\sqrt{p_0(1-p_0)/n}}$$

Bấm:

```text
(p_hat-p0)÷√(p0×(1-p0)÷n)=
```

---

## Bấm nhanh từng bài mục 4

| Bài | Loại | Bấm trọng tâm | Kết quả kiểm tra |
|---:|---|---|---|
| 4.1 | kỳ vọng | `1.96×7.2÷√64`; `((1.96×7.2)÷1.5)^2`; `(168.5-170)÷(7.2÷√64)` | CI 95%: [166.736,170.264]; n≥89; Z=-1.6667 |
| 4.2 | kỳ vọng | `2.576×2.1÷√36`; `((2.576×2.1)÷0.8)^2`; `(12.4-13)÷(2.1÷√36)` | CI 99%: [11.4984,13.3016]; n≥46; Z=-1.7143 |
| 4.3 | kỳ vọng | `1.645×1.3÷√100`; `((1.645×1.3)÷0.25)^2`; `(7.1-7.0)÷(1.3÷√100)` | CI 90%: [6.8862,7.3139]; n≥74; Z=0.7692 |
| 4.4 | kỳ vọng | `1.96×4.5÷√49`; `((1.96×4.5)÷1)^2`; `(50.8-52)÷(4.5÷√49)` | CI 95%: [49.54,52.06]; n≥78; Z=-1.8667 |
| 4.5 | kỳ vọng | `2.326×1.8÷√81`; `((2.326×1.8)÷0.5)^2`; `(9.6-9.2)÷(1.8÷√81)` | CI 98%: [9.1348,10.0652]; n≥71; Z=2.0000 |
| 4.6 | tỷ lệ | `52÷400`; `1.96×√(0.13×0.87÷400)`; `1.96^2×0.13×0.87÷0.03^2`; `(0.13-0.1)÷√(0.1×0.9÷400)` | p̂=0.13; CI [0.0970,0.1630]; n≥483; Z=2.0000 |
| 4.7 | tỷ lệ | `75÷625`; `2.576×√(0.12×0.88÷625)`; `2.576^2×0.12×0.88÷0.025^2`; `(0.12-0.15)÷√(0.15×0.85÷625)` | p̂=0.12; CI [0.0865,0.1535]; n≥1121; Z=-2.1004 |
| 4.8 | tỷ lệ | `138÷300`; `1.645×√(0.46×0.54÷300)`; `1.645^2×0.46×0.54÷0.05^2`; `(0.46-0.5)÷√(0.5×0.5÷300)` | p̂=0.46; CI [0.4127,0.5073]; n≥269; Z=-1.3856 |
| 4.9 | tỷ lệ | `240÷1000`; `1.96×√(0.24×0.76÷1000)`; `1.96^2×0.24×0.76÷0.02^2`; `(0.24-0.2)÷√(0.2×0.8÷1000)` | p̂=0.24; CI [0.2135,0.2665]; n≥1752; Z=3.1623 |
| 4.10 | tỷ lệ | `30÷250`; `2.326×√(0.12×0.88÷250)`; `2.326^2×0.12×0.88÷0.04^2`; `(0.12-0.1)÷√(0.1×0.9÷250)` | p̂=0.12; CI [0.0722,0.1678]; n≥358; Z=1.0541 |

Mẹo làm bài kiểm định:

1. Ghi đúng `H0`, `H1`.
2. Tính thống kê kiểm định `Z`.
3. So với ngưỡng tới hạn.
4. Kết luận bằng ngôn ngữ đề bài, không chỉ ghi “bác bỏ/không bác bỏ”.

---

# MỤC 5. TƯƠNG QUAN VÀ HỒI QUY TUYẾN TÍNH

## Bấm bằng STAT trên fx-570

### Vào chế độ hồi quy tuyến tính

```text
MODE → STAT → A+BX
```

Nhập từng cặp `(X,Y)` vào bảng.

Sau khi nhập xong:

### Lấy hệ số tương quan r

```text
SHIFT → 1(STAT) → Reg → r → =
```

### Lấy hệ số a, b của phương trình

Phương trình máy cho:

$$Y=a+bX$$

Bấm:

```text
SHIFT → 1(STAT) → Reg → A → =
SHIFT → 1(STAT) → Reg → B → =
```

### Dự đoán Y khi X=x0

Có 2 cách:

Cách 1: lấy `a`, `b`, rồi bấm:

```text
a + b×x0 =
```

Cách 2 nếu máy có chức năng dự đoán:

```text
x0 → SHIFT → 1(STAT) → Reg → ŷ → =
```

## Nhận xét nhanh hệ số tương quan

| |r| | Mức độ |
|---:|---|
| 0 đến 0.3 | yếu |
| 0.3 đến 0.7 | trung bình |
| 0.7 đến 0.9 | mạnh |
| 0.9 đến 1 | rất mạnh |

Dấu của `r`:

- `r > 0`: tương quan thuận.
- `r < 0`: tương quan nghịch.

---

## Bấm nhanh từng bài mục 5

### Bài 5.1

Nhập STAT A+BX các cặp:

```text
(2,20), (3,25), (5,37), (6,42), (8,55), (9,60)
```

Lấy `r`, `A`, `B`.

Kết quả kiểm tra:

```text
r≈0.9982
Y = 8.8571 + 5.6429X
Y(7)≈48.3571
```

---

### Bài 5.2

Nhập:

```text
(1,4.2), (2,5.0), (3,5.6), (4,6.4), (5,7.1), (6,7.8), (7,8.4)
```

Kết quả:

```text
r≈0.9983
Y = 3.5714 + 0.6929X
Y(8)≈9.1143
```

---

### Bài 5.3

Nhập:

```text
(20,120), (22,128), (24,135), (26,150), (28,165), (30,178)
```

Kết quả:

```text
r≈0.9894
Y = -2.8571 + 5.9143X
Y(27)≈156.8286
```

---

### Bài 5.4

Nhập:

```text
(1,5), (2,7), (3,9), (4,13), (5,16), (6,20)
```

Kết quả:

```text
r≈0.9912
Y = 1.8667 + 2.8857X
Y(7)≈22.0667
```

---

### Bài 5.5

Nhập:

```text
(10,100), (12,92), (14,85), (16,70), (18,63), (20,55)
```

Kết quả:

```text
r≈-0.9920
Y = 147.3333 - 4.7X
Y(15)≈76.8333
```

---

### Bài 5.6

Nhập:

```text
(5,40), (7,52), (8,58), (10,73), (12,86), (15,105)
```

Kết quả:

```text
r≈0.9991
Y = 4.5513 + 6.6923X
Y(11)≈78.1667
```

---

### Bài 5.7

Nhập:

```text
(30,2.0), (35,2.5), (40,3.5), (45,4.0), (50,5.4), (55,6.1)
```

Kết quả:

```text
r≈0.9892
Y = -3.0629 + 0.1646X
Y(48)≈4.8371
```

---

### Bài 5.8

Nhập:

```text
(1,8), (2,13), (3,17), (4,22), (5,26), (6,31)
```

Kết quả:

```text
r≈0.9994
Y = 3.6667 + 4.5333X
Y(7)≈35.4000
```

---

### Bài 5.9

Nhập:

```text
(3,4), (5,7), (7,10), (9,13), (11,18), (13,20)
```

Kết quả:

```text
r≈0.9949
Y = -1.0667 + 1.6464X
Y(10)≈15.3970
```

---

### Bài 5.10

Nhập:

```text
(1,9), (3,13), (4,15), (6,19), (8,25), (10,30)
```

Kết quả:

```text
r≈0.9977
Y = 6.1872 + 2.3498X
Y(7)≈22.6355
```

---

# MẸO NHANH XỬ LÝ ĐỀ XSTK

## 1. Nhìn từ khóa để chọn công thức

| Từ khóa trong đề | Dạng cần dùng |
|---|---|
| “chọn 1 nhóm/hộp/dây chuyền rồi…” | Xác suất đầy đủ |
| “biết rằng đã xảy ra…” | Bayes / xác suất có điều kiện |
| “ít nhất 1” | Thường dùng biến cố đối |
| “rút cùng lúc”, “chọn k phần tử” | Tổ hợp `nCr` |
| `X~N(μ,σ²)` | Phân phối chuẩn, nhớ lấy `σ=√σ²` |
| “tìm T sao cho P(X<T)=…” | InvN với Area bên trái |
| “P(X>T)=q” | Đổi thành `P(X<T)=1-q` |
| “mật độ f(x)” | Tích phân để tìm k, E, Var |
| “khoảng tin cậy” | Ước lượng ± sai số |
| “mức ý nghĩa 5%” | Kiểm định Z với mốc 1.645 hoặc 1.96 |
| “tương quan, hồi quy” | STAT → A+BX |

## 2. Các lỗi sai hay gặp

1. Nhầm phương sai với độ lệch chuẩn trong phân phối chuẩn.
2. Quên mẫu số Bayes là xác suất đầy đủ.
3. Với “ít nhất”, cộng thiếu trường hợp hoặc không dùng biến cố đối.
4. Với tổ hợp, dùng nhầm chỉnh hợp khi thứ tự không quan trọng.
5. Với kiểm định hai phía, quên dùng `|Z| > 1.96`.
6. Với hồi quy, nhầm phương trình `Y=a+bX` thành `X=a+bY`.
7. Với mật độ, quên điều kiện tổng tích phân bằng 1 trước khi tính E và Var.

## 3. Chiến thuật làm bài nhanh khi thi

### Dạng Bayes

Vẽ cây 2 tầng:

```text
Nhóm / nguồn → kết quả quan sát
```

Tử số Bayes = đúng nhánh cần hỏi.  
Mẫu số Bayes = tổng tất cả nhánh tạo ra kết quả đã biết.

### Dạng chuẩn

Luôn viết 3 dòng:

```text
σ = √phương_sai
Z1 = (a-μ)/σ, Z2 = (b-μ)/σ
P = Φ(Z2)-Φ(Z1)
```

### Dạng mật độ

Luôn làm theo thứ tự:

```text
1. Tìm k
2. Tính E(X)
3. Tính E(X²)
4. Var(X)=E(X²)-E²(X)
5. Tính xác suất theo cận đề cho
```

### Dạng thống kê

Tách ngay đề thành 2 loại:

```text
Có trung bình, độ lệch chuẩn → bài kỳ vọng μ
Có số trường hợp x trên n → bài tỷ lệ p
```

### Dạng hồi quy

Bấm máy trước lấy `r`, `A`, `B`, sau đó mới nhận xét:

```text
r gần 1: thuận rất mạnh
r gần -1: nghịch rất mạnh
r gần 0: yếu
```

---

# CHECKLIST TRƯỚC KHI NỘP BÀI

- [ ] Đã ghi rõ đề hoặc tóm tắt dữ kiện.
- [ ] Đã chọn đúng công thức.
- [ ] Với chuẩn: đã lấy đúng `σ`, không lấy nhầm phương sai.
- [ ] Với Bayes: tử số và mẫu số đúng biến cố.
- [ ] Với tổ hợp: mẫu số là toàn bộ không gian mẫu.
- [ ] Với kiểm định: kết luận theo đúng chiều của đối thuyết.
- [ ] Với hồi quy: ghi đúng dạng phương trình `Y=a+bX`.
- [ ] Kết quả làm tròn thống nhất 4 chữ số.
