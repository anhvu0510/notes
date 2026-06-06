# MỤC 3 - BÀI GIẢI CHI TIẾT: BIẾN NGẪU NHIÊN LIÊN TỤC 1 BIẾN

> File này tách riêng Mục 3. Mỗi bài có đề, cách nhận diện hàm mật độ, cách tìm `k`, kỳ vọng, phương sai và xác suất.

---

# Khung tư duy Mục 3

Với biến ngẫu nhiên liên tục, xác suất không tính bằng `P(X=x)`. Xác suất được tính bằng **diện tích dưới hàm mật độ**.

Nếu đề cho:

```math
f(x)=kg(x),\quad a<x<b
```

thì làm đúng thứ tự:

```text
Bước 1: Tìm k từ điều kiện tổng xác suất bằng 1.
Bước 2: Tính E(X).
Bước 3: Tính E(X²).
Bước 4: Tính Var(X)=E(X²)-[E(X)]².
Bước 5: Tính xác suất theo khoảng đề hỏi.
```

Công thức:

```math
\int_a^b f(x)dx=1
```

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

---

# Bài 3.1

## Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=kx,\quad 0<x<2.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(0.5<X<1.5)`.

## Nhận diện

Đây là hàm mật độ có hằng số `k`. Trước khi tính kỳ vọng hay xác suất, bắt buộc phải tìm `k` để hàm có tổng diện tích bằng 1.

## Giải từng bước

### a. Tìm k

Vì `f(x)` là mật độ nên:

```math
\int_0^2kx\,dx=1
```

Đưa `k` ra ngoài:

```math
k\int_0^2x\,dx=1
```

```math
k\left[\frac{x^2}{2}\right]_0^2=1
```

```math
k\cdot2=1\Rightarrow k=0.5
```

### b. Tính kỳ vọng và phương sai

Sau khi có `k`, ta có:

```math
f(x)=0.5x
```

Kỳ vọng:

```math
E(X)=\int_0^2x\cdot0.5x\,dx=0.5\int_0^2x^2dx
```

```math
E(X)=0.5\left[\frac{x^3}{3}\right]_0^2=\frac43=1.3333
```

Moment bậc hai:

```math
E(X^2)=\int_0^2x^2\cdot0.5x\,dx=0.5\int_0^2x^3dx
```

```math
E(X^2)=0.5\left[\frac{x^4}{4}\right]_0^2=2
```

Phương sai:

```math
Var(X)=2-\left(\frac43\right)^2=0.2222
```

### c. Tính xác suất

```math
P(0.5<X<1.5)=\int_{0.5}^{1.5}0.5x\,dx
```

```math
=0.5\left[\frac{x^2}{2}\right]_{0.5}^{1.5}=0.5000
```

## Kết luận

```text
k=0.5, E(X)=1.3333, Var(X)=0.2222, P=0.5000
```

---

# Bài 3.2

## Đề bài

```math
f(x)=kx^2,\quad 0<x<3.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1<X<2)`.

## Giải từng bước

### a. Tìm k

```math
\int_0^3kx^2dx=1
```

```math
k\left[\frac{x^3}{3}\right]_0^3=1
```

```math
k\cdot9=1\Rightarrow k=\frac19=0.1111
```

### b. Kỳ vọng và phương sai

```math
f(x)=\frac19x^2
```

```math
E(X)=\int_0^3x\cdot\frac19x^2dx=\frac19\int_0^3x^3dx
```

```math
E(X)=\frac19\left[\frac{x^4}{4}\right]_0^3=2.2500
```

```math
E(X^2)=\int_0^3x^2\cdot\frac19x^2dx=\frac19\int_0^3x^4dx
```

```math
E(X^2)=\frac19\left[\frac{x^5}{5}\right]_0^3=5.4000
```

```math
Var(X)=5.4000-2.2500^2=0.3375
```

### c. Xác suất

```math
P(1<X<2)=\int_1^2\frac19x^2dx
```

```math
=\frac19\left[\frac{x^3}{3}\right]_1^2=0.2593
```

## Kết luận

```text
k=0.1111, E=2.2500, Var=0.3375, P=0.2593
```

---

# Bài 3.3

## Đề bài

```math
f(x)=k(x+1),\quad 0<x<2.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(0.5<X<1.5)`.

## Giải từng bước

```math
\int_0^2k(x+1)dx=1
```

```math
k\left[\frac{x^2}{2}+x\right]_0^2=1
```

```math
k(2+2)=1\Rightarrow k=0.25
```

```math
E(X)=\int_0^2x\cdot0.25(x+1)dx=0.25\int_0^2(x^2+x)dx=1.1667
```

```math
E(X^2)=\int_0^2x^2\cdot0.25(x+1)dx=0.25\int_0^2(x^3+x^2)dx=1.6667
```

```math
Var(X)=1.6667-1.1667^2=0.3056
```

```math
P(0.5<X<1.5)=\int_{0.5}^{1.5}0.25(x+1)dx=0.5000
```

## Kết luận

```text
k=0.25, E=1.1667, Var=0.3056, P=0.5000
```

---

# Bài 3.4

## Đề bài

```math
f(x)=k(4-x),\quad 0<x<4.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1<X<3)`.

## Giải từng bước

```math
\int_0^4k(4-x)dx=1
```

```math
k\left[4x-\frac{x^2}{2}\right]_0^4=1
```

```math
k(16-8)=1\Rightarrow k=0.125
```

```math
E(X)=\int_0^4x\cdot0.125(4-x)dx=1.3333
```

```math
E(X^2)=\int_0^4x^2\cdot0.125(4-x)dx=2.6667
```

```math
Var(X)=2.6667-1.3333^2=0.8889
```

```math
P(1<X<3)=\int_1^30.125(4-x)dx=0.5000
```

## Kết luận

```text
k=0.125, E=1.3333, Var=0.8889, P=0.5000
```

---

# Bài 3.5

## Đề bài

```math
f(x)=\frac{k}{x^2},\quad 1<x<3.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1.5<X<2.5)`.

## Giải từng bước

Tìm `k`:

```math
\int_1^3\frac{k}{x^2}dx=1
```

Vì:

```math
\int x^{-2}dx=-x^{-1}=-\frac1x
```

nên:

```math
k\left[-\frac1x\right]_1^3=1
```

```math
k\left(1-\frac13\right)=1\Rightarrow k\cdot\frac23=1\Rightarrow k=1.5
```

Kỳ vọng:

```math
E(X)=\int_1^3x\cdot\frac{1.5}{x^2}dx=1.5\int_1^3\frac1xdx
```

```math
E(X)=1.5[\ln x]_1^3=1.5\ln3=1.6479
```

Moment bậc hai:

```math
E(X^2)=\int_1^3x^2\cdot\frac{1.5}{x^2}dx=1.5\int_1^3dx=3
```

```math
Var(X)=3-1.6479^2=0.2827
```

Xác suất:

```math
P(1.5<X<2.5)=\int_{1.5}^{2.5}\frac{1.5}{x^2}dx=0.4000
```

## Kết luận

```text
k=1.5, E=1.6479, Var=0.2827, P=0.4000
```

---

# Bài 3.6

## Đề bài

```math
f(x)=k\sin x,\quad 0<x<\pi.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(\pi/6<X<\pi/2)`.

## Giải từng bước

```math
\int_0^\pi k\sin xdx=1
```

```math
k[-\cos x]_0^\pi=1
```

```math
k(1-(-1))=1\Rightarrow 2k=1\Rightarrow k=0.5
```

Kỳ vọng:

```math
E(X)=\int_0^\pi x\cdot0.5\sin xdx=1.5708
```

Giải thích: hàm `sin x` trên `(0,π)` đối xứng quanh `π/2`, nên trung bình nằm tại `π/2`.

```math
E(X^2)=\int_0^\pi x^2\cdot0.5\sin xdx=2.9348
```

```math
Var(X)=2.9348-1.5708^2=0.4674
```

```math
P(\pi/6<X<\pi/2)=\int_{\pi/6}^{\pi/2}0.5\sin xdx=0.4330
```

## Kết luận

```text
k=0.5, E=1.5708, Var=0.4674, P=0.4330
```

---

# Bài 3.7

## Đề bài

```math
f(x)=k(1-x^2),\quad -1<x<1.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(-0.5<X<0.5)`.

## Giải từng bước

```math
\int_{-1}^{1}k(1-x^2)dx=1
```

```math
k\left[x-\frac{x^3}{3}\right]_{-1}^{1}=1
```

```math
k\cdot\frac43=1\Rightarrow k=0.75
```

Vì miền `(-1,1)` đối xứng và hàm mật độ cũng đối xứng:

```math
E(X)=0
```

```math
E(X^2)=\int_{-1}^{1}x^2\cdot0.75(1-x^2)dx=0.2000
```

```math
Var(X)=0.2000-0^2=0.2000
```

```math
P(-0.5<X<0.5)=\int_{-0.5}^{0.5}0.75(1-x^2)dx=0.6875
```

## Kết luận

```text
k=0.75, E=0, Var=0.2, P=0.6875
```

---

# Bài 3.8

## Đề bài

```math
f(x)=k(2x+1),\quad 0<x<1.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(0.25<X<0.75)`.

## Giải từng bước

```math
\int_0^1k(2x+1)dx=1
```

```math
k[x^2+x]_0^1=1\Rightarrow 2k=1\Rightarrow k=0.5
```

```math
E(X)=\int_0^1x\cdot0.5(2x+1)dx=0.5833
```

```math
E(X^2)=\int_0^1x^2\cdot0.5(2x+1)dx=0.4167
```

```math
Var(X)=0.4167-0.5833^2=0.0764
```

```math
P(0.25<X<0.75)=\int_{0.25}^{0.75}0.5(2x+1)dx=0.5000
```

## Kết luận

```text
k=0.5, E=0.5833, Var=0.0764, P=0.5000
```

---

# Bài 3.9

## Đề bài

```math
f(x)=ke^{-x/2},\quad x>0.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1<X<4)`.

## Giải từng bước

Tìm `k`:

```math
\int_0^{+\infty}ke^{-x/2}dx=1
```

Vì:

```math
\int_0^{+\infty}e^{-x/2}dx=2
```

nên:

```math
2k=1\Rightarrow k=0.5
```

Khi đó:

```math
f(x)=0.5e^{-x/2}
```

Đây là phân phối mũ dạng `λe^{-λx}` với `λ=0.5`, nên:

```math
E(X)=\frac1λ=2
```

```math
Var(X)=\frac1{λ^2}=4
```

Xác suất:

```math
P(1<X<4)=\int_1^40.5e^{-x/2}dx=e^{-1/2}-e^{-2}=0.4712
```

## Kết luận

```text
k=0.5, E=2, Var=4, P=0.4712
```

---

# Bài 3.10

## Đề bài

```math
f(x)=kxe^{-x},\quad x>0.
```

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1<X<3)`.

## Giải từng bước

Tìm `k`:

```math
\int_0^{+\infty}kxe^{-x}dx=1
```

Ta có:

```math
\int_0^{+\infty}xe^{-x}dx=1
```

nên:

```math
k=1
```

Kỳ vọng:

```math
E(X)=\int_0^{+\infty}x\cdot xe^{-x}dx=\int_0^{+\infty}x^2e^{-x}dx=2
```

Moment bậc hai:

```math
E(X^2)=\int_0^{+\infty}x^2\cdot xe^{-x}dx=\int_0^{+\infty}x^3e^{-x}dx=6
```

Phương sai:

```math
Var(X)=6-2^2=2
```

Xác suất:

```math
P(1<X<3)=\int_1^3xe^{-x}dx=0.5768
```

## Kết luận

```text
k=1, E=2, Var=2, P=0.5768
```
