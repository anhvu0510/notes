# MỤC 2 - BÀI GIẢI CHI TIẾT: BIẾN NGẪU NHIÊN LIÊN TỤC PHÂN PHỐI CHUẨN

> File này tách riêng Mục 2. Mỗi bài có đề, dữ kiện, cách đọc `N(μ,σ²)`, chuẩn hóa, tra bảng đầy đủ và kết luận.

---

# Khung tư duy Mục 2

Khi đề ghi:

```math
X\sim N(\mu,\sigma^2)
```

phải hiểu:

```text
μ  = trung bình/kỳ vọng
σ² = phương sai
σ  = độ lệch chuẩn = √σ²
```

Sai nhiều nhất là lấy luôn tham số thứ hai làm `σ`. Không được. Ví dụ `N(60,64)` thì `σ=8`, không phải `64`.

Để tính xác suất, đổi về chuẩn tắc:

```math
Z=\frac{X-\mu}{\sigma}\sim N(0,1)
```

Với khoảng:

```math
P(a<X<b)=\Phi\left(\frac{b-\mu}{\sigma}\right)-\Phi\left(\frac{a-\mu}{\sigma}\right)
```

Với tìm mốc `T`:

```math
P(X<T)=p\Rightarrow T=\mu+\sigma z_p
```

Nếu đề cho xác suất bên phải:

```math
P(X>T)=p\Rightarrow P(X<T)=1-p
```

---

# Bảng tra chuẩn dùng trong Mục 2

| z | Φ(z)=P(Z<z) |
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

---

# Bài 2.1

## Đề bài

Cho biến ngẫu nhiên `X ~ N(60, 64)`.

a. Tính `P(50 < X < 70)`.  
b. Tìm `T` sao cho `P(X < T) = 0.90`.

## Dữ kiện

```math
\mu=60,\quad \sigma^2=64,\quad \sigma=\sqrt{64}=8
```

## Giải câu a

Cần tính xác suất X nằm giữa 50 và 70. Vì bảng chuẩn dùng Z, phải đổi 50 và 70 sang z.

Cận dưới:

```math
z_1=\frac{50-60}{8}=-1.25
```

Cận trên:

```math
z_2=\frac{70-60}{8}=1.25
```

Suy ra:

```math
P(50<X<70)=P(-1.25<Z<1.25)
```

Theo bảng:

```math
\Phi(-1.25)=0.1056,\quad \Phi(1.25)=0.8944
```

```math
P=0.8944-0.1056=0.7888\approx0.7887
```

## Giải câu b

`P(X<T)=0.90` nghĩa là diện tích bên trái T bằng 90%.

Tra bảng:

```math
\Phi(1.2816)=0.90
```

nên:

```math
\frac{T-60}{8}=1.2816
```

```math
T=60+8\cdot1.2816=70.2528\approx70.2524
```

## Kết luận

```text
a/ 0.7887
b/ T≈70.2524
```

---

# Bài 2.2

## Đề bài

Cho biến ngẫu nhiên `X ~ N(100, 225)`.

a. Tính `P(85 < X < 120)`.  
b. Tìm `T` sao cho `P(X < T) = 0.95`.

## Dữ kiện

```math
\mu=100,\quad \sigma=\sqrt{225}=15
```

## Giải

Cận dưới:

```math
z_1=\frac{85-100}{15}=-1
```

Cận trên:

```math
z_2=\frac{120-100}{15}=1.3333
```

```math
P(85<X<120)=\Phi(1.3333)-\Phi(-1)
```

Từ bảng:

```math
\Phi(1.3333)=0.9088,\quad \Phi(-1)=0.1587
```

```math
P=0.9088-0.1587=0.7501
```

Câu b:

```math
P(X<T)=0.95\Rightarrow z_{0.95}=1.6449
```

```math
T=100+15\cdot1.6449=124.6735\approx124.6728
```

## Kết luận

```text
a/ 0.7501
b/ T≈124.6728
```

---

# Bài 2.3

## Đề bài

Cho biến ngẫu nhiên `X ~ N(500, 1600)`.

a. Tính `P(450 < X < 560)`.  
b. Tìm `T` sao cho `P(X < T) = 0.10`.

## Dữ kiện

```math
\mu=500,\quad \sigma=\sqrt{1600}=40
```

## Giải

```math
z_1=\frac{450-500}{40}=-1.25
```

```math
z_2=\frac{560-500}{40}=1.5
```

```math
P=\Phi(1.5)-\Phi(-1.25)=0.9332-0.1056=0.8276\approx0.8275
```

Câu b:

`P(X<T)=0.10` là vùng 10% bên trái, nên T phải nhỏ hơn trung bình 500.

```math
z_{0.10}=-1.2816
```

```math
T=500+40(-1.2816)=448.736\approx448.7379
```

## Kết luận

```text
a/ 0.8275
b/ T≈448.7379
```

---

# Bài 2.4

## Đề bài

Cho biến ngẫu nhiên `X ~ N(170, 36)`.

a. Tính `P(160 < X < 180)`.  
b. Tìm `T` sao cho `P(X > T) = 0.80`.

## Dữ kiện

```math
\mu=170,\quad \sigma=6
```

## Giải

```math
z_1=\frac{160-170}{6}=-1.6667
```

```math
z_2=\frac{180-170}{6}=1.6667
```

```math
P=\Phi(1.6667)-\Phi(-1.6667)=0.9522-0.0478=0.9044
```

Câu b cho xác suất bên phải. Phải đổi sang bên trái:

```math
P(X>T)=0.80\Rightarrow P(X<T)=0.20
```

```math
z_{0.20}=-0.8416
```

```math
T=170+6(-0.8416)=164.9504\approx164.9503
```

## Kết luận

```text
a/ 0.9044
b/ T≈164.9503
```

---

# Bài 2.5

## Đề bài

Cho biến ngẫu nhiên `X ~ N(30, 16)`.

a. Tính `P(25 < X < 35)`.  
b. Tìm `T` sao cho `P(X > T) = 0.05`.

## Dữ kiện

```math
\mu=30,\quad \sigma=4
```

## Giải

```math
z_1=-1.25,\quad z_2=1.25
```

```math
P=\Phi(1.25)-\Phi(-1.25)=0.8944-0.1056=0.7888\approx0.7887
```

Câu b:

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

```text
a/ 0.7887
b/ T≈36.5794
```

---

# Bài 2.6

## Đề bài

Cho biến ngẫu nhiên `X ~ N(75, 100)`.

a. Tính `P(65 < X < 90)`.  
b. Tìm `T` sao cho `P(X < T) = 0.975`.

## Dữ kiện

```math
\mu=75,\quad \sigma=10
```

## Giải

```math
z_1=\frac{65-75}{10}=-1
```

```math
z_2=\frac{90-75}{10}=1.5
```

```math
P=\Phi(1.5)-\Phi(-1)=0.9332-0.1587=0.7745
```

```math
z_{0.975}=1.96
```

```math
T=75+10\cdot1.96=94.6000
```

## Kết luận

```text
a/ 0.7745
b/ T=94.6000
```

---

# Bài 2.7

## Đề bài

Cho biến ngẫu nhiên `X ~ N(12, 6.25)`.

a. Tính `P(9 < X < 15)`.  
b. Tìm `T` sao cho `P(X < T) = 0.20`.

## Dữ kiện

```math
\mu=12,\quad \sigma=2.5
```

## Giải

```math
z_1=\frac{9-12}{2.5}=-1.2
```

```math
z_2=\frac{15-12}{2.5}=1.2
```

```math
P=\Phi(1.2)-\Phi(-1.2)=0.8849-0.1151=0.7698\approx0.7699
```

```math
z_{0.20}=-0.8416
```

```math
T=12+2.5(-0.8416)=9.8960
```

## Kết luận

```text
a/ 0.7699
b/ T≈9.8960
```

---

# Bài 2.8

## Đề bài

Cho biến ngẫu nhiên `X ~ N(200, 625)`.

a. Tính `P(180 < X < 230)`.  
b. Tìm `T` sao cho `P(X > T) = 0.85`.

## Dữ kiện

```math
\mu=200,\quad \sigma=25
```

## Giải

```math
z_1=-0.8,\quad z_2=1.2
```

```math
P=\Phi(1.2)-\Phi(-0.8)=0.8849-0.2119=0.6730\approx0.6731
```

```math
P(X>T)=0.85\Rightarrow P(X<T)=0.15
```

```math
z_{0.15}=-1.0364
```

```math
T=200+25(-1.0364)=174.0900\approx174.0908
```

## Kết luận

```text
a/ 0.6731
b/ T≈174.0908
```

---

# Bài 2.9

## Đề bài

Cho biến ngẫu nhiên `X ~ N(3.5, 0.16)`.

a. Tính `P(3.0 < X < 4.1)`.  
b. Tìm `T` sao cho `P(X < T) = 0.99`.

## Dữ kiện

```math
\mu=3.5,\quad \sigma=0.4
```

## Giải

```math
z_1=-1.25,\quad z_2=1.5
```

```math
P=\Phi(1.5)-\Phi(-1.25)=0.9332-0.1056=0.8276\approx0.8275
```

```math
z_{0.99}=2.3263
```

```math
T=3.5+0.4(2.3263)=4.4305
```

## Kết luận

```text
a/ 0.8275
b/ T≈4.4305
```

---

# Bài 2.10

## Đề bài

Cho biến ngẫu nhiên `X ~ N(1000, 14400)`.

a. Tính `P(850 < X < 1100)`.  
b. Tìm `T` sao cho `P(X > T) = 0.15`.

## Dữ kiện

```math
\mu=1000,\quad \sigma=120
```

## Giải

```math
z_1=\frac{850-1000}{120}=-1.25
```

```math
z_2=\frac{1100-1000}{120}=0.8333
```

```math
P=\Phi(0.8333)-\Phi(-1.25)=0.7977-0.1056=0.6921\approx0.6920
```

```math
P(X>T)=0.15\Rightarrow P(X<T)=0.85
```

```math
z_{0.85}=1.0364
```

```math
T=1000+120(1.0364)=1124.368\approx1124.3700
```

## Kết luận

```text
a/ 0.6920
b/ T≈1124.3700
```
