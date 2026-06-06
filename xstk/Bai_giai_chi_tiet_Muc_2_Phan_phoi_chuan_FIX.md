# MỤC 2 - BÀI GIẢI CHI TIẾT PHÂN PHỐI CHUẨN

> Bản này viết lại theo phong cách bài giảng: **Gọi - Ta có - Suy ra - Đáp số**, trình bày rõ từng phép chuẩn hóa, từng giá trị tra bảng, và không còn ghi chung chung “tra bảng”.

---

# 0. KIẾN THỨC NỀN TRƯỚC KHI LÀM

## 0.1. Đọc đúng ký hiệu phân phối chuẩn

Khi đề ghi:

```math
X \sim N(\mu,\sigma^2)
```

thì hiểu là:

```text
μ  = kỳ vọng/trung bình
σ² = phương sai
σ  = độ lệch chuẩn = căn bậc hai của phương sai
```

Sai lầm hay gặp:

```text
N(μ, σ²) cho phương sai, không phải độ lệch chuẩn.
```

Ví dụ:

```math
X\sim N(60,64)
```

thì:

```math
\mu=60,\quad \sigma^2=64,\quad \sigma=\sqrt{64}=8
```

---

## 0.2. Vì sao phải chuẩn hóa?

Bảng phân phối chuẩn thường chỉ dùng cho biến chuẩn tắc:

```math
Z\sim N(0,1)
```

Trong khi đề cho biến `X` có trung bình và phương sai riêng. Vì vậy phải đổi `X` về `Z` bằng công thức:

```math
Z=\frac{X-\mu}{\sigma}
```

Ý nghĩa:

```text
X - μ       = X lệch khỏi trung bình bao nhiêu
(X - μ)/σ   = độ lệch đó bằng bao nhiêu lần độ lệch chuẩn
```

---

## 0.3. Công thức tính xác suất khoảng

Muốn tính:

```math
P(a<X<b)
```

làm theo 3 bước:

```text
Bước 1: z1 = (a-μ)/σ
Bước 2: z2 = (b-μ)/σ
Bước 3: P(a<X<b)=P(z1<Z<z2)=Φ(z2)-Φ(z1)
```

Công thức:

```math
P(a<X<b)=\Phi\left(\frac{b-\mu}{\sigma}\right)-\Phi\left(\frac{a-\mu}{\sigma}\right)
```

---

## 0.4. Công thức tìm T

Nếu đề hỏi:

```math
P(X<T)=p
```

thì tìm `z_p` sao cho:

```math
\Phi(z_p)=p
```

Sau đó đổi ngược về X:

```math
T=\mu+\sigma z_p
```

Nếu đề hỏi:

```math
P(X>T)=p
```

thì phải đổi về xác suất bên trái:

```math
P(X<T)=1-p
```

rồi mới tra `z`.

---

# 1. BẢNG TRA CHUẨN DÙNG TRONG TOÀN BỘ MỤC 2

Trong phần giải bên dưới, mọi giá trị `Φ(z)` đều lấy từ bảng này.

| STT | `z` | `Φ(z)=P(Z<z)` | Dùng ở bài | Ghi chú |
|---:|---:|---:|---|---|
| 1 | `-1.6667` | `0.0478` | 2.4 | Cận dưới |
| 2 | `-1.2816` | `0.1000` | 2.3 | Phân vị 10% |
| 3 | `-1.2500` | `0.1056` | 2.1, 2.3, 2.5, 2.9, 2.10 | Cận dưới hay gặp |
| 4 | `-1.2000` | `0.1151` | 2.7 | Cận dưới |
| 5 | `-1.0364` | `0.1500` | 2.8 | Phân vị 15% |
| 6 | `-1.0000` | `0.1587` | 2.2, 2.6 | Cận dưới |
| 7 | `-0.8416` | `0.2000` | 2.4, 2.7 | Phân vị 20% |
| 8 | `-0.8000` | `0.2119` | 2.8 | Cận dưới |
| 9 | `0.8333` | `0.7977` | 2.10 | Cận trên |
| 10 | `1.0364` | `0.8500` | 2.10 | Phân vị 85% |
| 11 | `1.2000` | `0.8849` | 2.7, 2.8 | Cận trên |
| 12 | `1.2500` | `0.8944` | 2.1, 2.5 | Cận trên |
| 13 | `1.3333` | `0.9088` | 2.2 | Cận trên |
| 14 | `1.5000` | `0.9332` | 2.3, 2.6, 2.9 | Cận trên |
| 15 | `1.6449` | `0.9500` | 2.2, 2.5 | Phân vị 95% |
| 16 | `1.6667` | `0.9522` | 2.4 | Cận trên |
| 17 | `1.9600` | `0.9750` | 2.6 | Phân vị 97.5% |
| 18 | `2.3263` | `0.9900` | 2.9 | Phân vị 99% |

## Nếu dùng bảng Laplace trong tài liệu thầy/cô

Một số bảng không cho trực tiếp `Φ(z)`, mà cho phần diện tích từ `0` đến `z`. Gọi phần đó là `L(z)`:

```math
L(z)=\Phi(z)-0.5,\quad z>0
```

Suy ra:

```math
\Phi(z)=0.5+L(z)
```

Ví dụ bảng cho:

```math
L(1.96)=0.4750
```

thì:

```math
\Phi(1.96)=0.5+0.4750=0.9750
```

Với số âm, dùng quy tắc đối xứng:

```math
\Phi(-z)=1-\Phi(z)
```

Ví dụ:

```math
\Phi(-1.25)=1-\Phi(1.25)=1-0.8944=0.1056
```

---

# BÀI 2.1

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(60,64)
```

Yêu cầu:

a. Tính `P(50<X<70)`.  
b. Tìm `T` sao cho `P(X<T)=0.90`.

## Giải

Ta có:

```math
\mu=60,\quad \sigma^2=64\Rightarrow \sigma=8
```

### a. Tính `P(50<X<70)`

Gọi:

```math
Z=\frac{X-60}{8}\sim N(0,1)
```

Chuẩn hóa cận dưới:

```math
X=50\Rightarrow z_1=\frac{50-60}{8}=-1.25
```

Chuẩn hóa cận trên:

```math
X=70\Rightarrow z_2=\frac{70-60}{8}=1.25
```

Suy ra:

```math
P(50<X<70)=P(-1.25<Z<1.25)
```

Từ bảng:

```math
\Phi(-1.25)=0.1056,\quad \Phi(1.25)=0.8944
```

Vậy:

```math
P=0.8944-0.1056=0.7888\approx0.7887
```

### b. Tìm `T`

Ta cần:

```math
P(X<T)=0.90
```

Đổi sang chuẩn tắc:

```math
P\left(Z<\frac{T-60}{8}\right)=0.90
```

Từ bảng:

```math
\Phi(1.2816)=0.90
```

Do đó:

```math
\frac{T-60}{8}=1.2816
```

```math
T=60+8\cdot1.2816=70.2528\approx70.2524
```

## Đáp số

```text
a/ 0.7887
b/ T ≈ 70.2524
```

---

# BÀI 2.2

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(100,225)
```

Yêu cầu:

a. Tính `P(85<X<120)`.  
b. Tìm `T` sao cho `P(X<T)=0.95`.

## Giải

Ta có:

```math
\mu=100,\quad \sigma^2=225\Rightarrow \sigma=15
```

### a. Tính `P(85<X<120)`

```math
z_1=\frac{85-100}{15}=-1
```

```math
z_2=\frac{120-100}{15}=1.3333
```

Suy ra:

```math
P(85<X<120)=P(-1<Z<1.3333)
```

Từ bảng:

```math
\Phi(-1)=0.1587,\quad \Phi(1.3333)=0.9088
```

```math
P=0.9088-0.1587=0.7501
```

### b. Tìm `T`

```math
P(X<T)=0.95
```

Từ bảng:

```math
\Phi(1.6449)=0.95
```

Nên:

```math
\frac{T-100}{15}=1.6449
```

```math
T=100+15\cdot1.6449=124.6735\approx124.6728
```

## Đáp số

```text
a/ 0.7501
b/ T ≈ 124.6728
```

---

# BÀI 2.3

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(500,1600)
```

Yêu cầu:

a. Tính `P(450<X<560)`.  
b. Tìm `T` sao cho `P(X<T)=0.10`.

## Giải

Ta có:

```math
\mu=500,\quad \sigma^2=1600\Rightarrow \sigma=40
```

### a. Tính xác suất

```math
z_1=\frac{450-500}{40}=-1.25
```

```math
z_2=\frac{560-500}{40}=1.5
```

```math
P(450<X<560)=P(-1.25<Z<1.5)
```

Từ bảng:

```math
\Phi(-1.25)=0.1056,\quad \Phi(1.5)=0.9332
```

```math
P=0.9332-0.1056=0.8276\approx0.8275
```

### b. Tìm `T`

```math
P(X<T)=0.10
```

Từ bảng:

```math
\Phi(-1.2816)=0.10
```

Nên:

```math
\frac{T-500}{40}=-1.2816
```

```math
T=500+40\cdot(-1.2816)=448.736\approx448.7379
```

## Đáp số

```text
a/ 0.8275
b/ T ≈ 448.7379
```

---

# BÀI 2.4

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(170,36)
```

Yêu cầu:

a. Tính `P(160<X<180)`.  
b. Tìm `T` sao cho `P(X>T)=0.80`.

## Giải

Ta có:

```math
\mu=170,\quad \sigma^2=36\Rightarrow \sigma=6
```

### a. Tính xác suất

```math
z_1=\frac{160-170}{6}=-1.6667
```

```math
z_2=\frac{180-170}{6}=1.6667
```

```math
P(160<X<180)=P(-1.6667<Z<1.6667)
```

Từ bảng:

```math
\Phi(-1.6667)=0.0478,\quad \Phi(1.6667)=0.9522
```

```math
P=0.9522-0.0478=0.9044
```

### b. Tìm `T`

Đề cho xác suất bên phải:

```math
P(X>T)=0.80
```

Phải đổi sang xác suất bên trái:

```math
P(X<T)=1-0.80=0.20
```

Từ bảng:

```math
\Phi(-0.8416)=0.20
```

Nên:

```math
\frac{T-170}{6}=-0.8416
```

```math
T=170+6\cdot(-0.8416)=164.9504\approx164.9503
```

## Đáp số

```text
a/ 0.9044
b/ T ≈ 164.9503
```

---

# BÀI 2.5

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(30,16)
```

Yêu cầu:

a. Tính `P(25<X<35)`.  
b. Tìm `T` sao cho `P(X>T)=0.05`.

## Giải

```math
\mu=30,\quad \sigma^2=16\Rightarrow \sigma=4
```

### a. Tính xác suất

```math
z_1=\frac{25-30}{4}=-1.25
```

```math
z_2=\frac{35-30}{4}=1.25
```

```math
P(25<X<35)=P(-1.25<Z<1.25)
```

Từ bảng:

```math
\Phi(-1.25)=0.1056,\quad \Phi(1.25)=0.8944
```

```math
P=0.8944-0.1056=0.7888\approx0.7887
```

### b. Tìm `T`

```math
P(X>T)=0.05\Rightarrow P(X<T)=0.95
```

Từ bảng:

```math
\Phi(1.6449)=0.95
```

```math
T=30+4\cdot1.6449=36.5796\approx36.5794
```

## Đáp số

```text
a/ 0.7887
b/ T ≈ 36.5794
```

---

# BÀI 2.6

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(75,100)
```

Yêu cầu:

a. Tính `P(65<X<90)`.  
b. Tìm `T` sao cho `P(X<T)=0.975`.

## Giải

```math
\mu=75,\quad \sigma^2=100\Rightarrow \sigma=10
```

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

Từ bảng:

```math
\Phi(-1)=0.1587,\quad \Phi(1.5)=0.9332
```

```math
P=0.9332-0.1587=0.7745
```

### b. Tìm `T`

```math
P(X<T)=0.975
```

Từ bảng:

```math
\Phi(1.9600)=0.975
```

```math
T=75+10\cdot1.96=94.6000
```

## Đáp số

```text
a/ 0.7745
b/ T = 94.6000
```

---

# BÀI 2.7

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(12,6.25)
```

Yêu cầu:

a. Tính `P(9<X<15)`.  
b. Tìm `T` sao cho `P(X<T)=0.20`.

## Giải

```math
\mu=12,\quad \sigma^2=6.25\Rightarrow \sigma=2.5
```

### a. Tính xác suất

```math
z_1=\frac{9-12}{2.5}=-1.2
```

```math
z_2=\frac{15-12}{2.5}=1.2
```

```math
P(9<X<15)=P(-1.2<Z<1.2)
```

Từ bảng:

```math
\Phi(-1.2)=0.1151,\quad \Phi(1.2)=0.8849
```

```math
P=0.8849-0.1151=0.7698\approx0.7699
```

### b. Tìm `T`

```math
P(X<T)=0.20
```

Từ bảng:

```math
\Phi(-0.8416)=0.20
```

```math
T=12+2.5\cdot(-0.8416)=9.8960
```

## Đáp số

```text
a/ 0.7699
b/ T ≈ 9.8960
```

---

# BÀI 2.8

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(200,625)
```

Yêu cầu:

a. Tính `P(180<X<230)`.  
b. Tìm `T` sao cho `P(X>T)=0.85`.

## Giải

```math
\mu=200,\quad \sigma^2=625\Rightarrow \sigma=25
```

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

Từ bảng:

```math
\Phi(-0.8)=0.2119,\quad \Phi(1.2)=0.8849
```

```math
P=0.8849-0.2119=0.6730\approx0.6731
```

### b. Tìm `T`

```math
P(X>T)=0.85\Rightarrow P(X<T)=0.15
```

Từ bảng:

```math
\Phi(-1.0364)=0.15
```

```math
T=200+25\cdot(-1.0364)=174.0900\approx174.0908
```

## Đáp số

```text
a/ 0.6731
b/ T ≈ 174.0908
```

---

# BÀI 2.9

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(3.5,0.16)
```

Yêu cầu:

a. Tính `P(3.0<X<4.1)`.  
b. Tìm `T` sao cho `P(X<T)=0.99`.

## Giải

```math
\mu=3.5,\quad \sigma^2=0.16\Rightarrow \sigma=0.4
```

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

Từ bảng:

```math
\Phi(-1.25)=0.1056,\quad \Phi(1.5)=0.9332
```

```math
P=0.9332-0.1056=0.8276\approx0.8275
```

### b. Tìm `T`

```math
P(X<T)=0.99
```

Từ bảng:

```math
\Phi(2.3263)=0.99
```

```math
T=3.5+0.4\cdot2.3263=4.4305
```

## Đáp số

```text
a/ 0.8275
b/ T ≈ 4.4305
```

---

# BÀI 2.10

## Đề bài

Cho biến ngẫu nhiên:

```math
X\sim N(1000,14400)
```

Yêu cầu:

a. Tính `P(850<X<1100)`.  
b. Tìm `T` sao cho `P(X>T)=0.15`.

## Giải

```math
\mu=1000,\quad \sigma^2=14400\Rightarrow \sigma=120
```

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

Từ bảng:

```math
\Phi(-1.25)=0.1056,\quad \Phi(0.8333)=0.7977
```

```math
P=0.7977-0.1056=0.6921\approx0.6920
```

> Nếu dùng bảng làm tròn thô có thể ra xấp xỉ `0.6915`. Với bảng chuẩn chính xác hơn, nên ghi khoảng `0.6920`.

### b. Tìm `T`

```math
P(X>T)=0.15\Rightarrow P(X<T)=0.85
```

Từ bảng:

```math
\Phi(1.0364)=0.85
```

```math
T=1000+120\cdot1.0364=1124.368\approx1124.3700
```

## Đáp số

```text
a/ 0.6920
b/ T ≈ 1124.3700
```

---

# 2. CHECKLIST RIÊNG CHO MỤC 2

```text
[ ] Đọc đúng μ và σ².
[ ] Tính σ = căn của phương sai.
[ ] Với P(a<X<b), chuẩn hóa đủ cả 2 cận.
[ ] Dùng P(a<X<b)=Φ(z2)-Φ(z1).
[ ] Với P(X<T)=p, tìm z sao cho Φ(z)=p.
[ ] Với P(X>T)=p, đổi thành P(X<T)=1-p.
[ ] Đổi ngược T=μ+σz.
[ ] Kiểm tra hợp lý:
    - P(X<T) nhỏ => T < μ.
    - P(X<T) lớn => T > μ.
    - P(X>T) lớn => T thường nằm bên trái μ.
    - P(X>T) nhỏ => T thường nằm bên phải μ.
```
