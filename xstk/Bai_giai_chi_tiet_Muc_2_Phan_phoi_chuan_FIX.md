# MỤC 2 - BÀI GIẢI CHI TIẾT PHÂN PHỐI CHUẨN

> File này là bản sửa chi tiết cho **Mục 2. Biến ngẫu nhiên liên tục phân phối chuẩn**.  
> Mục tiêu: người mất gốc đọc vào hiểu vì sao phải chuẩn hóa, vì sao đổi xác suất bên phải sang bên trái, vì sao dùng `z_p`, và cách trình bày trong phòng thi.

---

# 0. CÁCH HIỂU PHÂN PHỐI CHUẨN TỪ MẤT GỐC

## 0.1. Phân phối chuẩn là gì?

Khi đề ghi:

```math
X \sim N(\mu,\sigma^2)
```

nghĩa là biến ngẫu nhiên `X` có phân phối chuẩn với:

- `μ`: trung bình.
- `σ²`: phương sai.
- `σ`: độ lệch chuẩn.

Điểm rất dễ sai:

```text
N(μ, σ²) cho phương sai, không phải độ lệch chuẩn.
```

Vì vậy luôn phải tính:

```math
\sigma=\sqrt{\sigma^2}
```

Ví dụ:

```math
X\sim N(60,64)
```

thì:

```math
\mu=60,\quad \sigma^2=64,\quad \sigma=8
```

Không được lấy `σ=64`.

---

## 0.2. Vì sao phải chuẩn hóa?

Bảng chuẩn thường dùng cho biến chuẩn tắc:

```math
Z\sim N(0,1)
```

Nhưng đề lại cho biến `X` có trung bình và độ lệch chuẩn khác nhau. Vì vậy phải đổi từ `X` sang `Z` bằng công thức:

```math
Z=\frac{X-\mu}{\sigma}
```

Ý nghĩa:

- `X-μ`: xem giá trị X lệch khỏi trung bình bao nhiêu.
- Chia cho `σ`: đổi độ lệch đó ra số lần độ lệch chuẩn.

Ví dụ nếu `Z=1.25`, nghĩa là giá trị X đang nằm cao hơn trung bình `1.25` lần độ lệch chuẩn.

---

## 0.3. Công thức tính xác suất khoảng

Muốn tính:

```math
P(a<X<b)
```

thì đổi cả hai cận `a`, `b` sang chuẩn tắc:

```math
z_1=\frac{a-\mu}{\sigma},\quad z_2=\frac{b-\mu}{\sigma}
```

Sau đó:

```math
P(a<X<b)=P(z_1<Z<z_2)=\Phi(z_2)-\Phi(z_1)
```

Trong đó `Φ(z)=P(Z<z)` là xác suất nằm bên trái điểm `z`.

---

## 0.4. Công thức tìm T

Nếu đề hỏi:

```math
P(X<T)=p
```

thì làm như sau:

```text
Bước 1: Tìm z_p sao cho P(Z<z_p)=p.
Bước 2: Đổi ngược về X bằng T=μ+σz_p.
```

Công thức:

```math
T=\mu+\sigma z_p
```

Nếu đề hỏi:

```math
P(X>T)=p
```

thì đây là xác suất bên phải. Đổi về bên trái:

```math
P(X<T)=1-p
```

rồi mới tìm `z`.

---

## 0.5. Các mốc z thường dùng

| Xác suất bên trái `p` | `z_p` |
|---:|---:|
| 0.10 | -1.2816 |
| 0.15 | -1.0364 |
| 0.20 | -0.8416 |
| 0.85 | 1.0364 |
| 0.90 | 1.2816 |
| 0.95 | 1.6449 |
| 0.975 | 1.9600 |
| 0.99 | 2.3263 |

---

# BÀI 2.1

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(60,64)
```

Yêu cầu:

a. Tính `P(50<X<70)`.  
b. Tìm `T` sao cho `P(X<T)=0.90`.

## Phân tích đề

Đề cho `N(60,64)`, nên:

```math
\mu=60,\quad \sigma^2=64,\quad \sigma=\sqrt{64}=8
```

Câu a hỏi xác suất nằm giữa 2 cận `50` và `70`, nên cần chuẩn hóa cả 2 cận.  
Câu b hỏi tìm mốc T sao cho diện tích bên trái bằng `0.90`, nên dùng phân vị chuẩn.

## Giải chi tiết

### a. Tính `P(50<X<70)`

Chuẩn hóa cận dưới:

```math
z_1=\frac{50-60}{8}=\frac{-10}{8}=-1.25
```

Chuẩn hóa cận trên:

```math
z_2=\frac{70-60}{8}=\frac{10}{8}=1.25
```

Vậy:

```math
P(50<X<70)=P(-1.25<Z<1.25)
```

Đổi sang hàm phân phối chuẩn:

```math
P(-1.25<Z<1.25)=\Phi(1.25)-\Phi(-1.25)
```

Tra bảng hoặc bấm máy:

```math
\Phi(1.25)=0.8944,\quad \Phi(-1.25)=0.1056
```

Do đó:

```math
P=0.8944-0.1056=0.7888\approx0.7887
```

### b. Tìm T sao cho `P(X<T)=0.90`

Ta cần mốc `z` sao cho:

```math
P(Z<z)=0.90
```

Tra bảng chuẩn:

```math
z_{0.90}=1.2816
```

Đổi ngược về biến X:

```math
T=\mu+\sigma z=60+8\cdot1.2816=70.2528\approx70.2524
```

## Kết luận

- a. `P(50<X<70)=0.7887`.
- b. `T≈70.2524`.

## Mẹo áp dụng

Khoảng đối xứng quanh trung bình `60`: từ `50` đến `70`. Hai z sẽ đối nhau: `-1.25` và `1.25`.

---

# BÀI 2.2

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(100,225)
```

Yêu cầu:

a. Tính `P(85<X<120)`.  
b. Tìm `T` sao cho `P(X<T)=0.95`.

## Phân tích đề

```math
\mu=100,\quad \sigma^2=225,\quad \sigma=15
```

Câu a là xác suất khoảng. Câu b là tìm phân vị 95%.

## Giải chi tiết

### a. Tính xác suất

Chuẩn hóa cận dưới:

```math
z_1=\frac{85-100}{15}=-1
```

Chuẩn hóa cận trên:

```math
z_2=\frac{120-100}{15}=1.3333
```

Vậy:

```math
P(85<X<120)=P(-1<Z<1.3333)
```

```math
P=\Phi(1.3333)-\Phi(-1)
```

Tra bảng:

```math
\Phi(1.3333)\approx0.9088,\quad \Phi(-1)=0.1587
```

```math
P=0.9088-0.1587=0.7501
```

### b. Tìm T

```math
P(X<T)=0.95
```

Tức là:

```math
P(Z<z)=0.95
```

Tra bảng:

```math
z_{0.95}=1.6449
```

```math
T=100+15\cdot1.6449=124.6728
```

## Kết luận

- a. `0.7501`.
- b. `T≈124.6728`.

---

# BÀI 2.3

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(500,1600)
```

Yêu cầu:

a. Tính `P(450<X<560)`.  
b. Tìm `T` sao cho `P(X<T)=0.10`.

## Phân tích đề

```math
\mu=500,\quad \sigma^2=1600,\quad \sigma=40
```

Câu b có xác suất `0.10`, tức T nằm ở vùng thấp bên trái phân phối.

## Giải chi tiết

### a. Tính xác suất khoảng

```math
z_1=\frac{450-500}{40}=-1.25
```

```math
z_2=\frac{560-500}{40}=1.5
```

```math
P(450<X<560)=P(-1.25<Z<1.5)
```

```math
P=\Phi(1.5)-\Phi(-1.25)
```

Tra bảng:

```math
\Phi(1.5)=0.9332,\quad \Phi(-1.25)=0.1056
```

```math
P=0.9332-0.1056=0.8276\approx0.8275
```

### b. Tìm T

```math
P(X<T)=0.10
```

Tra bảng chuẩn:

```math
z_{0.10}=-1.2816
```

Vì xác suất bên trái chỉ 10%, z âm là hợp lý.

```math
T=500+40\cdot(-1.2816)=448.736\approx448.7379
```

## Kết luận

- a. `0.8275`.
- b. `T≈448.7379`.

---

# BÀI 2.4

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(170,36)
```

Yêu cầu:

a. Tính `P(160<X<180)`.  
b. Tìm `T` sao cho `P(X>T)=0.80`.

## Phân tích đề

```math
\mu=170,\quad \sigma^2=36,\quad \sigma=6
```

Câu b là điểm dễ sai vì đề cho xác suất bên phải `P(X>T)`. Bảng chuẩn thường tìm xác suất bên trái `P(X<T)`, nên phải đổi:

```math
P(X<T)=1-0.80=0.20
```

## Giải chi tiết

### a. Tính xác suất khoảng

```math
z_1=\frac{160-170}{6}=-1.6667
```

```math
z_2=\frac{180-170}{6}=1.6667
```

```math
P(160<X<180)=P(-1.6667<Z<1.6667)
```

Tra bảng hoặc bấm máy:

```math
P=0.9044
```

### b. Tìm T

Từ đề:

```math
P(X>T)=0.80
```

Đổi sang bên trái:

```math
P(X<T)=0.20
```

Tra bảng:

```math
z_{0.20}=-0.8416
```

Đổi về X:

```math
T=170+6\cdot(-0.8416)=164.9504\approx164.9503
```

## Kết luận

- a. `0.9044`.
- b. `T≈164.9503`.

---

# BÀI 2.5

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(30,16)
```

Yêu cầu:

a. Tính `P(25<X<35)`.  
b. Tìm `T` sao cho `P(X>T)=0.05`.

## Phân tích đề

```math
\mu=30,\quad \sigma=4
```

Câu a là khoảng đối xứng quanh trung bình. Câu b là xác suất bên phải 5%, nên T là mốc cao, nằm bên phải trung bình.

## Giải chi tiết

### a. Tính xác suất

```math
z_1=\frac{25-30}{4}=-1.25
```

```math
z_2=\frac{35-30}{4}=1.25
```

```math
P(25<X<35)=P(-1.25<Z<1.25)=0.7887
```

### b. Tìm T

```math
P(X>T)=0.05\Rightarrow P(X<T)=0.95
```

```math
z_{0.95}=1.6449
```

```math
T=30+4\cdot1.6449=36.5796\approx36.5794
```

## Kết luận

- a. `0.7887`.
- b. `T≈36.5794`.

---

# BÀI 2.6

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(75,100)
```

Yêu cầu:

a. Tính `P(65<X<90)`.  
b. Tìm `T` sao cho `P(X<T)=0.975`.

## Phân tích đề

```math
\mu=75,\quad \sigma^2=100,\quad \sigma=10
```

Câu b là phân vị 97.5%, đây là mốc rất hay gặp, tương ứng `z=1.96`.

## Giải chi tiết

### a. Tính xác suất

```math
z_1=\frac{65-75}{10}=-1
```

```math
z_2=\frac{90-75}{10}=1.5
```

```math
P(65<X<90)=P(-1<Z<1.5)
```

```math
P=\Phi(1.5)-\Phi(-1)=0.9332-0.1587=0.7745
```

### b. Tìm T

```math
P(X<T)=0.975
```

```math
z_{0.975}=1.96
```

```math
T=75+10\cdot1.96=94.6
```

## Kết luận

- a. `0.7745`.
- b. `T=94.6000`.

---

# BÀI 2.7

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(12,6.25)
```

Yêu cầu:

a. Tính `P(9<X<15)`.  
b. Tìm `T` sao cho `P(X<T)=0.20`.

## Phân tích đề

```math
\mu=12,\quad \sigma=\sqrt{6.25}=2.5
```

Câu b xác suất bên trái 20%, nên T nằm bên trái trung bình.

## Giải chi tiết

### a. Tính xác suất

```math
z_1=\frac{9-12}{2.5}=-1.2
```

```math
z_2=\frac{15-12}{2.5}=1.2
```

```math
P(9<X<15)=P(-1.2<Z<1.2)=0.7699
```

### b. Tìm T

```math
z_{0.20}=-0.8416
```

```math
T=12+2.5\cdot(-0.8416)=9.8960
```

## Kết luận

- a. `0.7699`.
- b. `T≈9.8960`.

---

# BÀI 2.8

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(200,625)
```

Yêu cầu:

a. Tính `P(180<X<230)`.  
b. Tìm `T` sao cho `P(X>T)=0.85`.

## Phân tích đề

```math
\mu=200,\quad \sigma=25
```

Câu b cho xác suất bên phải rất lớn 85%, nên mốc T phải nằm bên trái trung bình. Do đó kết quả T nhỏ hơn 200 là hợp lý.

## Giải chi tiết

### a. Tính xác suất

```math
z_1=\frac{180-200}{25}=-0.8
```

```math
z_2=\frac{230-200}{25}=1.2
```

```math
P(180<X<230)=P(-0.8<Z<1.2)
```

```math
P=\Phi(1.2)-\Phi(-0.8)=0.8849-0.2119=0.6730\approx0.6731
```

### b. Tìm T

```math
P(X>T)=0.85
```

Đổi về bên trái:

```math
P(X<T)=1-0.85=0.15
```

```math
z_{0.15}=-1.0364
```

```math
T=200+25\cdot(-1.0364)=174.0900\approx174.0908
```

## Kết luận

- a. `0.6731`.
- b. `T≈174.0908`.

---

# BÀI 2.9

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(3.5,0.16)
```

Yêu cầu:

a. Tính `P(3.0<X<4.1)`.  
b. Tìm `T` sao cho `P(X<T)=0.99`.

## Phân tích đề

```math
\mu=3.5,\quad \sigma=\sqrt{0.16}=0.4
```

Câu b xác suất bên trái 99%, nên T nằm khá xa bên phải trung bình.

## Giải chi tiết

### a. Tính xác suất

```math
z_1=\frac{3.0-3.5}{0.4}=-1.25
```

```math
z_2=\frac{4.1-3.5}{0.4}=1.5
```

```math
P(3.0<X<4.1)=P(-1.25<Z<1.5)
```

```math
P=\Phi(1.5)-\Phi(-1.25)=0.9332-0.1056=0.8276\approx0.8275
```

### b. Tìm T

```math
z_{0.99}=2.3263
```

```math
T=3.5+0.4\cdot2.3263=4.4305
```

## Kết luận

- a. `0.8275`.
- b. `T≈4.4305`.

---

# BÀI 2.10

## Đề bài

Cho biến ngẫu nhiên:

```math
X \sim N(1000,14400)
```

Yêu cầu:

a. Tính `P(850<X<1100)`.  
b. Tìm `T` sao cho `P(X>T)=0.15`.

## Phân tích đề

```math
\mu=1000,\quad \sigma=\sqrt{14400}=120
```

Câu b: xác suất bên phải là 15%, vậy xác suất bên trái là 85%, nên T nằm bên phải trung bình.

## Giải chi tiết

### a. Tính xác suất

```math
z_1=\frac{850-1000}{120}=-1.25
```

```math
z_2=\frac{1100-1000}{120}=0.8333
```

```math
P(850<X<1100)=P(-1.25<Z<0.8333)
```

```math
P=\Phi(0.8333)-\Phi(-1.25)=0.7971-0.1056=0.6915
```

### b. Tìm T

```math
P(X>T)=0.15\Rightarrow P(X<T)=0.85
```

```math
z_{0.85}=1.0364
```

```math
T=1000+120\cdot1.0364=1124.368\approx1124.3700
```

## Kết luận

- a. `0.6915`.
- b. `T≈1124.3700`.

---

# CHECKLIST RIÊNG CHO MỤC 2

```text
[ ] Đọc đúng μ và σ².
[ ] Tính σ = căn của phương sai.
[ ] Với xác suất khoảng, chuẩn hóa cả 2 cận.
[ ] Với P(X<T), tìm z cùng diện tích bên trái.
[ ] Với P(X>T), đổi thành P(X<T)=1-p.
[ ] Tính T = μ + σz.
[ ] Kiểm tra hợp lý: xác suất bên trái nhỏ thì T phải bên trái μ; xác suất bên trái lớn thì T phải bên phải μ.
```
