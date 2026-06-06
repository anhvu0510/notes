# BÀI GIẢI CHI TIẾT XÁC SUẤT - THỐNG KÊ

> Phiên bản này viết theo kiểu **tài liệu mang vào phòng thi để tham khảo cách làm**: mỗi bài có **đề**, **nhận diện dạng**, **cách suy nghĩ**, **các bước giải**, **giải thích vì sao dùng công thức**, và **kết luận**.

Quy ước:

- Kết quả làm tròn 4 chữ số nếu không yêu cầu khác.
- `C(n,k)` là tổ hợp: chọn `k` phần tử từ `n` phần tử, không xét thứ tự.
- Nếu `X ~ N(μ, σ²)` thì `σ²` là phương sai, còn độ lệch chuẩn là `σ = √σ²`.
- Với kiểm định mức ý nghĩa 5%:
  - Kiểm định phải: bác bỏ `H0` nếu `Z > 1.645`.
  - Kiểm định trái: bác bỏ `H0` nếu `Z < -1.645`.
  - Kiểm định hai phía: bác bỏ `H0` nếu `|Z| > 1.96`.

---

# MỤC 1. XÁC SUẤT ĐẦY ĐỦ, BAYES, XÁC SUẤT CÓ ĐIỀU KIỆN

## Công thức nền

Khi kết quả cần tính có thể đến từ nhiều nguồn khác nhau, ta chia bài toán theo từng nguồn.

```math
P(A)=\sum_i P(H_i)P(A|H_i)
```

Công thức này gọi là **xác suất đầy đủ**. Hiểu đơn giản: xác suất xảy ra A bằng tổng xác suất đi qua từng nhánh để tạo ra A.

Khi đề nói “biết rằng A đã xảy ra” và hỏi xác suất thuộc nguồn nào, dùng Bayes:

```math
P(H_i|A)=\frac{P(H_i)P(A|H_i)}{P(A)}
```

Mẫu số `P(A)` thường chính là kết quả của câu trước.

---

## Bài 1.1. Dây chuyền sản xuất

### Đề bài

Một nhà máy có 3 dây chuyền A, B, C sản xuất lần lượt 40%, 35%, 25% tổng sản phẩm. Tỷ lệ sản phẩm lỗi tương ứng là 3%, 5%, 8%.

a. Tính xác suất chọn ngẫu nhiên được một sản phẩm bị lỗi.  
b. Biết sản phẩm được chọn bị lỗi, tính xác suất sản phẩm đó do dây chuyền C sản xuất.

### Nhận diện dạng bài

Sản phẩm lỗi có thể đến từ 3 nguồn: A, B hoặc C. Vì vậy câu a dùng xác suất đầy đủ. Câu b hỏi ngược lại: đã biết sản phẩm lỗi, hỏi nó đến từ dây chuyền nào, nên dùng Bayes.

### Cách suy nghĩ

Muốn một sản phẩm bị lỗi thì có 3 đường xảy ra:

1. Sản phẩm do A sản xuất và A làm lỗi.
2. Sản phẩm do B sản xuất và B làm lỗi.
3. Sản phẩm do C sản xuất và C làm lỗi.

Vì 3 trường hợp này không trùng nhau nên cộng lại.

### Giải

Gọi `L` là biến cố sản phẩm bị lỗi.

```math
P(A)=0.40,\quad P(B)=0.35,\quad P(C)=0.25
```

```math
P(L|A)=0.03,\quad P(L|B)=0.05,\quad P(L|C)=0.08
```

Câu a:

```math
P(L)=P(A)P(L|A)+P(B)P(L|B)+P(C)P(L|C)
```

```math
P(L)=0.40\cdot0.03+0.35\cdot0.05+0.25\cdot0.08
```

```math
P(L)=0.012+0.0175+0.020=0.0495
```

Câu b:

Cần tính `P(C|L)`. Dùng Bayes:

```math
P(C|L)=\frac{P(C)P(L|C)}{P(L)}
```

```math
P(C|L)=\frac{0.25\cdot0.08}{0.0495}=0.4040
```

### Kết luận

- a. Xác suất sản phẩm bị lỗi là `0.0495`.
- b. Nếu biết sản phẩm bị lỗi, xác suất sản phẩm do C sản xuất là `0.4040`.

---

## Bài 1.2. Chọn hộp rồi rút bi

### Đề bài

Có 3 hộp I, II, III được chọn với xác suất 0.30, 0.50, 0.20. Tỷ lệ bi đỏ trong các hộp lần lượt là 70%, 40%, 20%. Chọn 1 hộp rồi rút 1 bi.

a. Tính xác suất rút được bi đỏ.  
b. Biết đã rút được bi đỏ, tính xác suất bi đến từ hộp I.

### Nhận diện dạng bài

Kết quả “rút được đỏ” phụ thuộc vào việc chọn hộp nào trước. Đây là bài xác suất đầy đủ. Câu b hỏi ngược từ kết quả đỏ về nguồn hộp I nên dùng Bayes.

### Giải

Gọi `Đ` là biến cố rút được bi đỏ.

```math
P(Đ)=0.30\cdot0.70+0.50\cdot0.40+0.20\cdot0.20
```

```math
P(Đ)=0.21+0.20+0.04=0.45
```

Biết đã rút được đỏ, xác suất hộp được chọn là I:

```math
P(I|Đ)=\frac{P(I)P(Đ|I)}{P(Đ)}
```

```math
P(I|Đ)=\frac{0.30\cdot0.70}{0.45}=0.4667
```

### Kết luận

- a. `0.4500`.
- b. `0.4667`.

---

## Bài 1.3. Xét nghiệm bệnh

### Đề bài

Một bệnh có tỷ lệ mắc là 1%. Xét nghiệm dương tính với người bệnh là 95%, và dương tính giả với người không bệnh là 4%.

a. Tính xác suất xét nghiệm dương tính.  
b. Nếu kết quả dương tính, tính xác suất người đó thật sự mắc bệnh.

### Nhận diện dạng bài

Có 2 nhóm người: mắc bệnh và không mắc bệnh. Kết quả dương tính có thể đến từ cả 2 nhóm, nên câu a dùng xác suất đầy đủ. Câu b có dữ kiện “đã dương tính” nên dùng Bayes.

### Giải

Gọi:

- `B`: mắc bệnh.
- `K`: không mắc bệnh.
- `+`: xét nghiệm dương tính.

```math
P(B)=0.01,\quad P(K)=0.99
```

```math
P(+|B)=0.95,\quad P(+|K)=0.04
```

Câu a:

```math
P(+)=P(B)P(+|B)+P(K)P(+|K)
```

```math
P(+)=0.01\cdot0.95+0.99\cdot0.04=0.0095+0.0396=0.0491
```

Câu b:

```math
P(B|+)=\frac{P(B)P(+|B)}{P(+)}
```

```math
P(B|+)=\frac{0.01\cdot0.95}{0.0491}=0.1935
```

### Giải thích ý nghĩa

Dù xét nghiệm có độ nhạy 95%, bệnh rất hiếm nên số người không bệnh nhưng dương tính giả vẫn đáng kể. Vì vậy xác suất thật sự mắc bệnh sau khi dương tính chỉ khoảng 19.35%.

### Kết luận

- a. `0.0491`.
- b. `0.1935`.

---

## Bài 1.4. Hai xạ thủ

### Đề bài

Hai xạ thủ A và B bắn độc lập. Xác suất trúng của A là 0.75, của B là 0.60.

a. Tính xác suất cả hai cùng trúng.  
b. Biết đúng 1 viên trúng, tính xác suất viên trúng là của A.

### Nhận diện dạng bài

Hai người bắn độc lập nên xác suất cùng xảy ra bằng tích. Câu b là xác suất có điều kiện.

### Giải

Gọi `A` là A trúng, `B` là B trúng.

Câu a:

```math
P(A\cap B)=P(A)P(B)=0.75\cdot0.60=0.45
```

Câu b:

Đúng 1 viên trúng gồm 2 trường hợp:

- A trúng, B trật.
- A trật, B trúng.

```math
P(\text{đúng 1 trúng})=0.75\cdot0.40+0.25\cdot0.60=0.30+0.15=0.45
```

Trường hợp viên trúng là của A chính là A trúng và B trật:

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

### Đề bài

Rút ngẫu nhiên 5 lá bài từ bộ bài 52 lá.

a. Tính xác suất có ít nhất 1 lá Ách.  
b. Tính xác suất có đúng 2 lá Ách.

### Nhận diện dạng bài

Rút cùng lúc 5 lá, thứ tự không quan trọng, nên dùng tổ hợp. Bộ bài có 4 lá Ách và 48 lá không phải Ách.

### Giải

Tổng số cách rút 5 lá:

```math
C_{52}^5
```

Câu a:

“Ít nhất 1 Ách” gồm 1, 2, 3, 4 Ách. Nếu cộng trực tiếp sẽ dài. Ta dùng biến cố đối: không có Ách nào.

```math
P(\text{ít nhất 1 Ách})=1-P(\text{không có Ách})
```

Số cách không có Ách: chọn 5 lá từ 48 lá không Ách.

```math
P=1-\frac{C_{48}^5}{C_{52}^5}=0.3412
```

Câu b:

Đúng 2 Ách nghĩa là:

- Chọn 2 lá từ 4 lá Ách: `C_4^2`.
- Chọn 3 lá còn lại từ 48 lá không Ách: `C_48^3`.

```math
P=\frac{C_4^2C_{48}^3}{C_{52}^5}=0.0399
```

### Kết luận

- a. `0.3412`.
- b. `0.0399`.

---

## Bài 1.6. Rút bi cùng lúc

### Đề bài

Hộp có 8 bi xanh và 12 bi đỏ. Lấy cùng lúc 4 bi.

a. Xác suất đúng 2 bi xanh.  
b. Xác suất ít nhất 2 bi xanh.

### Nhận diện dạng bài

Lấy cùng lúc nên thứ tự không quan trọng, dùng tổ hợp.

Tổng số bi là `20`, tổng số cách lấy 4 bi là `C_20^4`.

### Giải

Câu a:

Đúng 2 xanh nghĩa là chọn 2 xanh từ 8 xanh và 2 đỏ từ 12 đỏ.

```math
P=\frac{C_8^2C_{12}^2}{C_{20}^4}=0.3814
```

Câu b:

Ít nhất 2 xanh gồm 3 trường hợp:

- 2 xanh, 2 đỏ.
- 3 xanh, 1 đỏ.
- 4 xanh, 0 đỏ.

```math
P=\frac{C_8^2C_{12}^2+C_8^3C_{12}^1+C_8^4}{C_{20}^4}=0.4696
```

### Kết luận

- a. `0.3814`.
- b. `0.4696`.

---

## Bài 1.7. Sinh viên đậu môn X

### Đề bài

Lớp có 25% năm nhất, 45% năm hai, 30% năm ba. Tỷ lệ đậu môn X tương ứng là 80%, 60%, 30%.

a. Tính xác suất sinh viên được chọn đậu môn X.  
b. Biết sinh viên đó đậu, tính xác suất sinh viên thuộc năm hai.

### Nhận diện dạng bài

Sinh viên đậu có thể thuộc năm nhất, năm hai hoặc năm ba. Câu a dùng xác suất đầy đủ. Câu b hỏi ngược lại từ dữ kiện đã đậu về nhóm năm hai, dùng Bayes.

### Giải

Gọi `D` là biến cố đậu môn X.

```math
P(D)=0.25\cdot0.80+0.45\cdot0.60+0.30\cdot0.30
```

```math
P(D)=0.20+0.27+0.09=0.56
```

Biết sinh viên đậu, xác suất thuộc năm hai:

```math
P(\text{năm hai}|D)=\frac{0.45\cdot0.60}{0.56}=0.4821
```

### Kết luận

- a. `0.5600`.
- b. `0.4821`.

---

## Bài 1.8. Chuyển bi giữa hai hộp

### Đề bài

Hộp A có 5 bi đỏ, 3 bi xanh. Hộp B có 4 bi đỏ, 6 bi xanh. Rút 1 bi từ A chuyển sang B, sau đó rút 1 bi từ B.

a. Tính xác suất rút ở B được bi đỏ.  
b. Biết rút ở B được bi đỏ, tính xác suất bi chuyển từ A sang là bi xanh.

### Nhận diện dạng bài

Màu bi rút ở B phụ thuộc vào màu bi chuyển từ A sang. Vì vậy phải chia thành 2 trường hợp: chuyển đỏ hoặc chuyển xanh.

### Giải

Trường hợp 1: chuyển đỏ từ A sang B.

```math
P(\text{chuyển đỏ})=\frac58
```

Khi đó B có 5 đỏ, 6 xanh, tổng 11 bi:

```math
P(\text{rút đỏ từ B}|\text{chuyển đỏ})=\frac5{11}
```

Trường hợp 2: chuyển xanh từ A sang B.

```math
P(\text{chuyển xanh})=\frac38
```

Khi đó B có 4 đỏ, 7 xanh, tổng 11 bi:

```math
P(\text{rút đỏ từ B}|\text{chuyển xanh})=\frac4{11}
```

Câu a:

```math
P(Đ_B)=\frac58\cdot\frac5{11}+\frac38\cdot\frac4{11}=0.4205
```

Câu b:

Biết đã rút được đỏ ở B, hỏi xác suất nhánh ban đầu là chuyển xanh. Đây là Bayes:

```math
P(\text{chuyển xanh}|Đ_B)=\frac{\frac38\cdot\frac4{11}}{0.4205}=0.3243
```

### Kết luận

- a. `0.4205`.
- b. `0.3243`.

---

## Bài 1.9. Tỷ lệ mắc bệnh theo giới tính

### Đề bài

Vùng dân cư có 55% nữ, 45% nam. Tỷ lệ mắc bệnh M ở nữ là 20%, ở nam là 10%.

a. Tính xác suất một người được chọn mắc bệnh M.  
b. Biết người đó mắc bệnh M, tính xác suất người đó là nam.

### Nhận diện dạng bài

Mắc bệnh có thể đến từ nhóm nữ hoặc nam. Câu a là xác suất đầy đủ, câu b là Bayes.

### Giải

Gọi `M` là biến cố mắc bệnh.

```math
P(M)=0.55\cdot0.20+0.45\cdot0.10=0.11+0.045=0.155
```

Biết mắc bệnh, xác suất là nam:

```math
P(\text{nam}|M)=\frac{0.45\cdot0.10}{0.155}=0.2903
```

### Kết luận

- a. `0.1550`.
- b. `0.2903`.

---

## Bài 1.10. Tung xu rồi rút bi

### Đề bài

Tung đồng xu cân đối. Nếu sấp, bỏ vào bình 1 đỏ và 2 vàng. Nếu ngửa, bỏ vào bình 2 đỏ và 2 vàng. Sau đó rút 1 bi.

a. Tính xác suất rút được bi đỏ.  
b. Biết rút được đỏ, tính xác suất đồng xu ra ngửa.

### Nhận diện dạng bài

Kết quả rút bi phụ thuộc vào kết quả tung xu. Có 2 nhánh: sấp và ngửa.

### Giải

Nếu sấp:

```math
P(\text{sấp})=\frac12,\quad P(Đ|\text{sấp})=\frac13
```

Nếu ngửa:

```math
P(\text{ngửa})=\frac12,\quad P(Đ|\text{ngửa})=\frac24
```

Câu a:

```math
P(Đ)=\frac12\cdot\frac13+\frac12\cdot\frac24=0.4167
```

Câu b:

```math
P(\text{ngửa}|Đ)=\frac{\frac12\cdot\frac24}{0.4167}=0.6000
```

### Kết luận

- a. `0.4167`.
- b. `0.6000`.

---

# MỤC 2. PHÂN PHỐI CHUẨN

## Cách suy nghĩ chung

Mọi bài phân phối chuẩn trong mục này đều làm theo 3 bước:

1. Xác định `μ` và `σ`. Nếu đề cho `N(μ, σ²)` thì phải lấy căn tham số thứ hai để ra `σ`.
2. Chuẩn hóa về `Z` bằng công thức:

```math
Z=\frac{X-\mu}{\sigma}
```

3. Dùng bảng chuẩn hoặc máy tính để lấy xác suất.

---

## Bài 2.1

### Đề bài

`X ~ N(60,64)`.  
a. Tính `P(50<X<70)`.  
b. Tìm `T` sao cho `P(X<T)=0.90`.

### Giải

Vì `σ²=64` nên:

```math
σ=\sqrt{64}=8
```

Câu a:

```math
P(50<X<70)=P\left(\frac{50-60}{8}<Z<\frac{70-60}{8}\right)
```

```math
=P(-1.25<Z<1.25)=\Phi(1.25)-\Phi(-1.25)=0.7887
```

Câu b:

`P(X<T)=0.90` nghĩa là `T` là phân vị 90%. Với chuẩn tắc:

```math
z_{0.90}=1.2816
```

Đổi ngược về X:

```math
T=\mu+σz=60+8\cdot1.2816=70.2524
```

### Kết luận

- a. `0.7887`.
- b. `T=70.2524`.

---

## Bài 2.2

### Đề bài

`X ~ N(100,225)`.  
a. Tính `P(85<X<120)`.  
b. Tìm `T` sao cho `P(X<T)=0.95`.

### Giải

```math
σ=\sqrt{225}=15
```

```math
P(85<X<120)=P\left(\frac{85-100}{15}<Z<\frac{120-100}{15}\right)
```

```math
=P(-1<Z<1.3333)=\Phi(1.3333)-\Phi(-1)=0.7501
```

Với `P(X<T)=0.95`, tra chuẩn tắc:

```math
z_{0.95}=1.6449
```

```math
T=100+15\cdot1.6449=124.6728
```

### Kết luận

- a. `0.7501`.
- b. `T=124.6728`.

---

## Bài 2.3

### Đề bài

`X ~ N(500,1600)`.  
a. Tính `P(450<X<560)`.  
b. Tìm `T` sao cho `P(X<T)=0.10`.

### Giải

```math
σ=\sqrt{1600}=40
```

```math
P(450<X<560)=P\left(\frac{450-500}{40}<Z<\frac{560-500}{40}\right)
```

```math
=P(-1.25<Z<1.5)=0.8275
```

Với `P(X<T)=0.10`:

```math
z_{0.10}=-1.2816
```

```math
T=500+40\cdot(-1.2816)=448.7379
```

### Kết luận

- a. `0.8275`.
- b. `T=448.7379`.

---

## Bài 2.4

### Đề bài

`X ~ N(170,36)`.  
a. Tính `P(160<X<180)`.  
b. Tìm `T` sao cho `P(X>T)=0.80`.

### Giải

```math
σ=\sqrt{36}=6
```

```math
P(160<X<180)=P\left(\frac{160-170}{6}<Z<\frac{180-170}{6}\right)
```

```math
=P(-1.6667<Z<1.6667)=0.9044
```

Câu b có xác suất bên phải. Đổi sang bên trái:

```math
P(X>T)=0.80\Rightarrow P(X<T)=0.20
```

```math
z_{0.20}=-0.8416
```

```math
T=170+6\cdot(-0.8416)=164.9503
```

### Kết luận

- a. `0.9044`.
- b. `T=164.9503`.

---

## Bài 2.5

### Đề bài

`X ~ N(30,16)`.  
a. Tính `P(25<X<35)`.  
b. Tìm `T` sao cho `P(X>T)=0.05`.

### Giải

```math
σ=\sqrt{16}=4
```

```math
P(25<X<35)=P(-1.25<Z<1.25)=0.7887
```

```math
P(X>T)=0.05\Rightarrow P(X<T)=0.95
```

```math
z_{0.95}=1.6449
```

```math
T=30+4\cdot1.6449=36.5794
```

### Kết luận

- a. `0.7887`.
- b. `T=36.5794`.

---

## Bài 2.6

### Đề bài

`X ~ N(75,100)`.  
a. Tính `P(65<X<90)`.  
b. Tìm `T` sao cho `P(X<T)=0.975`.

### Giải

```math
σ=10
```

```math
P(65<X<90)=P\left(\frac{65-75}{10}<Z<\frac{90-75}{10}\right)
```

```math
=P(-1<Z<1.5)=0.7745
```

```math
z_{0.975}=1.96
```

```math
T=75+10\cdot1.96=94.5996
```

### Kết luận

- a. `0.7745`.
- b. `T=94.5996`.

---

## Bài 2.7

### Đề bài

`X ~ N(12,6.25)`.  
a. Tính `P(9<X<15)`.  
b. Tìm `T` sao cho `P(X<T)=0.20`.

### Giải

```math
σ=\sqrt{6.25}=2.5
```

```math
P(9<X<15)=P(-1.2<Z<1.2)=0.7699
```

```math
z_{0.20}=-0.8416
```

```math
T=12+2.5\cdot(-0.8416)=9.8960
```

### Kết luận

- a. `0.7699`.
- b. `T=9.8960`.

---

## Bài 2.8

### Đề bài

`X ~ N(200,625)`.  
a. Tính `P(180<X<230)`.  
b. Tìm `T` sao cho `P(X>T)=0.85`.

### Giải

```math
σ=\sqrt{625}=25
```

```math
P(180<X<230)=P(-0.8<Z<1.2)=0.6731
```

Đổi xác suất bên phải sang bên trái:

```math
P(X>T)=0.85\Rightarrow P(X<T)=0.15
```

```math
z_{0.15}=-1.0364
```

```math
T=200+25\cdot(-1.0364)=174.0908
```

### Kết luận

- a. `0.6731`.
- b. `T=174.0908`.

---

## Bài 2.9

### Đề bài

`X ~ N(3.5,0.16)`.  
a. Tính `P(3.0<X<4.1)`.  
b. Tìm `T` sao cho `P(X<T)=0.99`.

### Giải

```math
σ=\sqrt{0.16}=0.4
```

```math
P(3.0<X<4.1)=P(-1.25<Z<1.5)=0.8275
```

```math
z_{0.99}=2.3263
```

```math
T=3.5+0.4\cdot2.3263=4.4305
```

### Kết luận

- a. `0.8275`.
- b. `T=4.4305`.

---

## Bài 2.10

### Đề bài

`X ~ N(1000,14400)`.  
a. Tính `P(850<X<1100)`.  
b. Tìm `T` sao cho `P(X>T)=0.15`.

### Giải

```math
σ=\sqrt{14400}=120
```

```math
P(850<X<1100)=P\left(\frac{850-1000}{120}<Z<\frac{1100-1000}{120}\right)
```

```math
=P(-1.25<Z<0.8333)=0.6915
```

```math
P(X>T)=0.15\Rightarrow P(X<T)=0.85
```

```math
z_{0.85}=1.0364
```

```math
T=1000+120\cdot1.0364=1124.3700
```

### Kết luận

- a. `0.6915`.
- b. `T=1124.3700`.

---

# MỤC 3. BIẾN NGẪU NHIÊN LIÊN TỤC 1 BIẾN

## Quy trình chung

Với mật độ `f(x)=kg(x)` trên khoảng `(a,b)`:

1. Tìm `k` từ điều kiện tổng xác suất bằng 1:

```math
\int_a^b kg(x)dx=1
```

2. Tính kỳ vọng:

```math
E(X)=\int_a^b xf(x)dx
```

3. Tính moment bậc hai:

```math
E(X^2)=\int_a^b x^2f(x)dx
```

4. Tính phương sai:

```math
Var(X)=E(X^2)-[E(X)]^2
```

5. Tính xác suất:

```math
P(c<X<d)=\int_c^d f(x)dx
```

---

## Bài 3.1

### Đề bài

`f(x)=kx, 0<x<2`. Tìm `k`, `E(X)`, `Var(X)`, `P(0.5<X<1.5)`.

### Giải

Tìm `k`:

```math
\int_0^2kx\,dx=1
```

```math
k\left[\frac{x^2}{2}\right]_0^2=1\Rightarrow 2k=1\Rightarrow k=0.5
```

Kỳ vọng:

```math
E(X)=\int_0^2x\cdot0.5x\,dx=0.5\int_0^2x^2dx=\frac43=1.3333
```

Moment bậc hai:

```math
E(X^2)=\int_0^2x^2\cdot0.5x\,dx=0.5\int_0^2x^3dx=2
```

Phương sai:

```math
Var(X)=2-\left(\frac43\right)^2=0.2222
```

Xác suất:

```math
P(0.5<X<1.5)=\int_{0.5}^{1.5}0.5x\,dx=0.5
```

### Kết luận

`k=0.5`, `E(X)=1.3333`, `Var(X)=0.2222`, xác suất `0.5000`.

---

## Bài 3.2

### Đề bài

`f(x)=kx², 0<x<3`. Tìm `k`, `E(X)`, `Var(X)`, `P(1<X<2)`.

### Giải

Tìm `k`:

```math
\int_0^3kx^2dx=1
```

```math
k\left[\frac{x^3}{3}\right]_0^3=1\Rightarrow 9k=1\Rightarrow k=\frac19=0.1111
```

Kỳ vọng:

```math
E(X)=\int_0^3x\cdot\frac19x^2dx=\frac19\int_0^3x^3dx
```

```math
E(X)=\frac19\cdot\frac{3^4}{4}=2.25
```

Moment bậc hai:

```math
E(X^2)=\frac19\int_0^3x^4dx=\frac19\cdot\frac{3^5}{5}=5.4
```

Phương sai:

```math
Var(X)=5.4-2.25^2=0.3375
```

Xác suất:

```math
P(1<X<2)=\int_1^2\frac19x^2dx=\frac19\left[\frac{x^3}{3}\right]_1^2=0.2593
```

### Kết luận

`k=0.1111`, `E(X)=2.2500`, `Var(X)=0.3375`, xác suất `0.2593`.

---

## Bài 3.3

### Đề bài

`f(x)=k(x+1), 0<x<2`. Tìm `k`, `E(X)`, `Var(X)`, `P(0.5<X<1.5)`.

### Giải

Tìm `k`:

```math
\int_0^2k(x+1)dx=1
```

```math
k\left[\frac{x^2}{2}+x\right]_0^2=1\Rightarrow k(2+2)=1\Rightarrow k=0.25
```

Kỳ vọng:

```math
E(X)=\int_0^2x\cdot0.25(x+1)dx
```

```math
E(X)=0.25\int_0^2(x^2+x)dx=1.1667
```

Moment bậc hai:

```math
E(X^2)=0.25\int_0^2(x^3+x^2)dx=1.6667
```

Phương sai:

```math
Var(X)=1.6667-1.1667^2=0.3056
```

Xác suất:

```math
P(0.5<X<1.5)=\int_{0.5}^{1.5}0.25(x+1)dx=0.5
```

### Kết luận

`k=0.25`, `E(X)=1.1667`, `Var(X)=0.3056`, xác suất `0.5000`.

---

## Bài 3.4

### Đề bài

`f(x)=k(4-x), 0<x<4`. Tìm `k`, `E(X)`, `Var(X)`, `P(1<X<3)`.

### Giải

Tìm `k`:

```math
\int_0^4k(4-x)dx=1
```

```math
k\left[4x-\frac{x^2}{2}\right]_0^4=1\Rightarrow 8k=1\Rightarrow k=0.125
```

Kỳ vọng:

```math
E(X)=\int_0^4x\cdot0.125(4-x)dx=1.3333
```

Moment bậc hai:

```math
E(X^2)=\int_0^4x^2\cdot0.125(4-x)dx=2.6667
```

Phương sai:

```math
Var(X)=2.6667-1.3333^2=0.8889
```

Xác suất:

```math
P(1<X<3)=\int_1^30.125(4-x)dx=0.5000
```

### Kết luận

`k=0.125`, `E(X)=1.3333`, `Var(X)=0.8889`, xác suất `0.5000`.

---

## Bài 3.5

### Đề bài

`f(x)=k/x², 1<x<3`. Tìm `k`, `E(X)`, `Var(X)`, `P(1.5<X<2.5)`.

### Giải

Tìm `k`:

```math
\int_1^3\frac{k}{x^2}dx=1
```

```math
k\left[-\frac1x\right]_1^3=1\Rightarrow k\left(1-\frac13\right)=1
```

```math
k\cdot\frac23=1\Rightarrow k=1.5
```

Kỳ vọng:

```math
E(X)=\int_1^3x\cdot\frac{1.5}{x^2}dx=1.5\int_1^3\frac1x dx
```

```math
E(X)=1.5\ln3=1.6479
```

Moment bậc hai:

```math
E(X^2)=\int_1^3x^2\cdot\frac{1.5}{x^2}dx=1.5\int_1^3dx=3
```

Phương sai:

```math
Var(X)=3-(1.6479)^2=0.2827
```

Xác suất:

```math
P(1.5<X<2.5)=\int_{1.5}^{2.5}\frac{1.5}{x^2}dx=0.4000
```

### Kết luận

`k=1.5`, `E(X)=1.6479`, `Var(X)=0.2827`, xác suất `0.4000`.

---

## Bài 3.6

### Đề bài

`f(x)=k sin x, 0<x<π`. Tìm `k`, `E(X)`, `Var(X)`, `P(π/6<X<π/2)`.

### Giải

Tìm `k`:

```math
\int_0^\pi k\sin xdx=1
```

```math
k[-\cos x]_0^\pi=1\Rightarrow k(2)=1\Rightarrow k=0.5
```

Kỳ vọng:

```math
E(X)=\int_0^\pi x\cdot0.5\sin xdx=1.5708
```

Ở đây hàm mật độ đối xứng quanh `π/2`, nên kỳ vọng bằng `π/2=1.5708`.

Moment bậc hai:

```math
E(X^2)=\int_0^\pi x^2\cdot0.5\sin xdx=2.9348
```

Phương sai:

```math
Var(X)=2.9348-(1.5708)^2=0.4674
```

Xác suất:

```math
P(\pi/6<X<\pi/2)=\int_{\pi/6}^{\pi/2}0.5\sin xdx=0.4330
```

### Kết luận

`k=0.5`, `E(X)=1.5708`, `Var(X)=0.4674`, xác suất `0.4330`.

---

## Bài 3.7

### Đề bài

`f(x)=k(1-x²), -1<x<1`. Tìm `k`, `E(X)`, `Var(X)`, `P(-0.5<X<0.5)`.

### Giải

Tìm `k`:

```math
\int_{-1}^{1}k(1-x^2)dx=1
```

```math
k\left[x-\frac{x^3}{3}\right]_{-1}^{1}=1\Rightarrow k\cdot\frac43=1\Rightarrow k=0.75
```

Kỳ vọng:

Vì miền `(-1,1)` đối xứng và mật độ cũng đối xứng, trung bình nằm tại 0:

```math
E(X)=0
```

Moment bậc hai:

```math
E(X^2)=\int_{-1}^{1}x^2\cdot0.75(1-x^2)dx=0.2
```

Phương sai:

```math
Var(X)=0.2-0^2=0.2
```

Xác suất:

```math
P(-0.5<X<0.5)=\int_{-0.5}^{0.5}0.75(1-x^2)dx=0.6875
```

### Kết luận

`k=0.75`, `E(X)=0`, `Var(X)=0.2`, xác suất `0.6875`.

---

## Bài 3.8

### Đề bài

`f(x)=k(2x+1), 0<x<1`. Tìm `k`, `E(X)`, `Var(X)`, `P(0.25<X<0.75)`.

### Giải

Tìm `k`:

```math
\int_0^1k(2x+1)dx=1
```

```math
k[x^2+x]_0^1=1\Rightarrow 2k=1\Rightarrow k=0.5
```

Kỳ vọng:

```math
E(X)=\int_0^1x\cdot0.5(2x+1)dx=0.5833
```

Moment bậc hai:

```math
E(X^2)=\int_0^1x^2\cdot0.5(2x+1)dx=0.4167
```

Phương sai:

```math
Var(X)=0.4167-0.5833^2=0.0764
```

Xác suất:

```math
P(0.25<X<0.75)=\int_{0.25}^{0.75}0.5(2x+1)dx=0.5000
```

### Kết luận

`k=0.5`, `E(X)=0.5833`, `Var(X)=0.0764`, xác suất `0.5000`.

---

## Bài 3.9

### Đề bài

`f(x)=ke^{-x/2}, x>0`. Tìm `k`, `E(X)`, `Var(X)`, `P(1<X<4)`.

### Giải

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

Đây chính là phân phối mũ với tham số `λ=0.5`.

Kỳ vọng và phương sai của phân phối mũ:

```math
E(X)=\frac1λ=2
```

```math
Var(X)=\frac1{λ^2}=4
```

Xác suất:

```math
P(1<X<4)=\int_1^40.5e^{-x/2}dx
```

```math
=e^{-1/2}-e^{-2}=0.4712
```

### Kết luận

`k=0.5`, `E(X)=2`, `Var(X)=4`, xác suất `0.4712`.

---

## Bài 3.10

### Đề bài

`f(x)=kxe^{-x}, x>0`. Tìm `k`, `E(X)`, `Var(X)`, `P(1<X<3)`.

### Giải

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

### Kết luận

`k=1`, `E(X)=2`, `Var(X)=2`, xác suất `0.5768`.

---

# MỤC 4. ƯỚC LƯỢNG VÀ KIỂM ĐỊNH

## Cách nhận diện

- Nếu đề cho `n, x̄, s`: thường là bài về kỳ vọng `μ`.
- Nếu đề cho `n` mẫu, có `x` trường hợp đạt tính chất A: thường là bài về tỷ lệ `p`.

## Công thức cần dùng

Khoảng tin cậy kỳ vọng:

```math
\bar x\pm z\frac{s}{\sqrt n}
```

Khoảng tin cậy tỷ lệ:

```math
\hat p\pm z\sqrt{\frac{\hat p(1-\hat p)}{n}}
```

Kiểm định kỳ vọng:

```math
Z=\frac{\bar x-\mu_0}{s/\sqrt n}
```

Kiểm định tỷ lệ:

```math
Z=\frac{\hat p-p_0}{\sqrt{p_0(1-p_0)/n}}
```

---

## Bài 4.1

### Đề bài

`n=64`, `x̄=168.5`, `s=7.2`.  
a. Ước lượng điểm cho kỳ vọng.  
b. Khoảng tin cậy 95%.  
c. Với `d=1.5`, tìm cỡ mẫu tối thiểu.  
d. Kiểm định `H0: μ=170`, `H1: μ<170`, mức ý nghĩa 5%.

### Giải

Câu a:

Ước lượng điểm cho kỳ vọng tổng thể chính là trung bình mẫu:

```math
\hat\mu=\bar x=168.5
```

Câu b:

Với độ tin cậy 95%, `z=1.96`.

Sai số:

```math
E=1.96\cdot\frac{7.2}{\sqrt{64}}=1.764
```

Khoảng tin cậy:

```math
168.5\pm1.764=[166.736;170.264]
```

Câu c:

```math
n\ge\left(\frac{1.96\cdot7.2}{1.5}\right)^2=88.47
```

Cỡ mẫu phải là số nguyên và phải đủ lớn, nên làm tròn lên:

```math
n=89
```

Câu d:

```math
Z=\frac{168.5-170}{7.2/\sqrt{64}}=-1.6667
```

Vì `H1: μ<170`, đây là kiểm định trái. Ở mức 5%, bác bỏ nếu `Z<-1.645`. Ta có `-1.6667<-1.645`, nên bác bỏ `H0`.

### Kết luận

Có đủ cơ sở ở mức ý nghĩa 5% để cho rằng kỳ vọng nhỏ hơn 170.

---

## Bài 4.2

### Đề bài

`n=36`, `x̄=12.4`, `s=2.1`. Khoảng tin cậy 99%, `d=0.8`, kiểm định `H0: μ=13`, `H1: μ≠13`.

### Giải

Ước lượng điểm:

```math
\hat\mu=12.4
```

Khoảng tin cậy 99%, `z=2.576`:

```math
E=2.576\cdot\frac{2.1}{\sqrt{36}}=0.9016
```

```math
CI=[12.4-0.9016;12.4+0.9016]=[11.4984;13.3016]
```

Cỡ mẫu:

```math
n\ge\left(\frac{2.576\cdot2.1}{0.8}\right)^2=45.69
```

Làm tròn lên: `n=46`.

Kiểm định:

```math
Z=\frac{12.4-13}{2.1/\sqrt{36}}=-1.7143
```

Vì `H1: μ≠13`, kiểm định hai phía. Bác bỏ nếu `|Z|>1.96`. Ở đây `|Z|=1.7143<1.96`, nên không bác bỏ `H0`.

### Kết luận

Chưa đủ cơ sở để kết luận kỳ vọng khác 13.

---

## Bài 4.3

### Đề bài

`n=100`, `x̄=7.1`, `s=1.3`. Khoảng tin cậy 90%, `d=0.25`, kiểm định `H0: μ=7.0`, `H1: μ>7.0`.

### Giải

Ước lượng điểm:

```math
\hat\mu=7.1
```

Khoảng tin cậy 90%, `z=1.645`:

```math
E=1.645\cdot\frac{1.3}{\sqrt{100}}=0.2139
```

```math
CI=[6.8862;7.3139]
```

Cỡ mẫu:

```math
n\ge\left(\frac{1.645\cdot1.3}{0.25}\right)^2=73.18
```

Làm tròn lên: `n=74`.

Kiểm định:

```math
Z=\frac{7.1-7.0}{1.3/\sqrt{100}}=0.7692
```

Vì kiểm định phải, bác bỏ nếu `Z>1.645`. Nhưng `0.7692<1.645`, nên không bác bỏ `H0`.

### Kết luận

Chưa đủ cơ sở để kết luận điểm trung bình lớn hơn 7.0.

---

## Bài 4.4

### Đề bài

`n=49`, `x̄=50.8`, `s=4.5`. Khoảng tin cậy 95%, `d=1.0`, kiểm định `H0: μ=52`, `H1: μ<52`.

### Giải

Ước lượng điểm:

```math
\hat\mu=50.8
```

Khoảng tin cậy 95%, `z=1.96`:

```math
E=1.96\cdot\frac{4.5}{\sqrt{49}}=1.26
```

```math
CI=[49.5400;52.0600]
```

Cỡ mẫu:

```math
n\ge\left(\frac{1.96\cdot4.5}{1.0}\right)^2=77.79
```

Làm tròn lên: `n=78`.

Kiểm định:

```math
Z=\frac{50.8-52}{4.5/\sqrt{49}}=-1.8667
```

Kiểm định trái, bác bỏ nếu `Z<-1.645`. Vì `-1.8667<-1.645`, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận khối lượng trung bình nhỏ hơn 52.

---

## Bài 4.5

### Đề bài

`n=81`, `x̄=9.6`, `s=1.8`. Khoảng tin cậy 98%, `d=0.5`, kiểm định `H0: μ=9.2`, `H1: μ>9.2`.

### Giải

Ước lượng điểm:

```math
\hat\mu=9.6
```

Khoảng tin cậy 98%, `z=2.326`:

```math
E=2.326\cdot\frac{1.8}{\sqrt{81}}=0.4652
```

```math
CI=[9.1348;10.0652]
```

Cỡ mẫu:

```math
n\ge\left(\frac{2.326\cdot1.8}{0.5}\right)^2=70.13
```

Làm tròn lên: `n=71`.

Kiểm định:

```math
Z=\frac{9.6-9.2}{1.8/\sqrt{81}}=2.0000
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `2.0000>1.645`, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận tuổi thọ pin trung bình lớn hơn 9.2.

---

## Bài 4.6

### Đề bài

Khảo sát `n=400`, có `x=52` trường hợp mang đặc tính A. Khoảng tin cậy 95%, `d=0.03`, kiểm định `H0:p=0.1`, `H1:p>0.1`.

### Giải

Ước lượng điểm:

```math
\hat p=\frac{52}{400}=0.13
```

Khoảng tin cậy 95%, `z=1.96`:

```math
E=1.96\sqrt{\frac{0.13(1-0.13)}{400}}=0.0330
```

```math
CI=[0.0970;0.1630]
```

Cỡ mẫu:

```math
n\ge\frac{1.96^2\cdot0.13\cdot0.87}{0.03^2}=482.84
```

Làm tròn lên: `n=483`.

Kiểm định:

```math
Z=\frac{0.13-0.1}{\sqrt{0.1(1-0.1)/400}}=2.0000
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `2.0000>1.645`, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận tỷ lệ lớn hơn 0.1.

---

## Bài 4.7

### Đề bài

`n=625`, `x=75`. Khoảng tin cậy 99%, `d=0.025`, kiểm định `H0:p=0.15`, `H1:p<0.15`.

### Giải

```math
\hat p=\frac{75}{625}=0.12
```

Khoảng tin cậy 99%, `z=2.576`:

```math
E=2.576\sqrt{\frac{0.12\cdot0.88}{625}}=0.0335
```

```math
CI=[0.0865;0.1535]
```

Cỡ mẫu:

```math
n\ge\frac{2.576^2\cdot0.12\cdot0.88}{0.025^2}=1120.82
```

Làm tròn lên: `n=1121`.

Kiểm định:

```math
Z=\frac{0.12-0.15}{\sqrt{0.15\cdot0.85/625}}=-2.1004
```

Kiểm định trái, bác bỏ nếu `Z<-1.645`. Vì `-2.1004<-1.645`, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận tỷ lệ nhỏ hơn 0.15.

---

## Bài 4.8

### Đề bài

`n=300`, `x=138`. Khoảng tin cậy 90%, `d=0.05`, kiểm định `H0:p=0.5`, `H1:p≠0.5`.

### Giải

```math
\hat p=\frac{138}{300}=0.46
```

Khoảng tin cậy 90%, `z=1.645`:

```math
E=1.645\sqrt{\frac{0.46\cdot0.54}{300}}=0.0473
```

```math
CI=[0.4127;0.5073]
```

Cỡ mẫu:

```math
n\ge\frac{1.645^2\cdot0.46\cdot0.54}{0.05^2}=268.89
```

Làm tròn lên: `n=269`.

Kiểm định:

```math
Z=\frac{0.46-0.5}{\sqrt{0.5\cdot0.5/300}}=-1.3856
```

Kiểm định hai phía, bác bỏ nếu `|Z|>1.96`. Vì `1.3856<1.96`, không bác bỏ `H0`.

### Kết luận

Chưa đủ cơ sở để kết luận tỷ lệ khác 0.5.

---

## Bài 4.9

### Đề bài

`n=1000`, `x=240`. Khoảng tin cậy 95%, `d=0.02`, kiểm định `H0:p=0.2`, `H1:p>0.2`.

### Giải

```math
\hat p=\frac{240}{1000}=0.24
```

Khoảng tin cậy 95%, `z=1.96`:

```math
E=1.96\sqrt{\frac{0.24\cdot0.76}{1000}}=0.0265
```

```math
CI=[0.2135;0.2665]
```

Cỡ mẫu:

```math
n\ge\frac{1.96^2\cdot0.24\cdot0.76}{0.02^2}=1751.77
```

Làm tròn lên: `n=1752`.

Kiểm định:

```math
Z=\frac{0.24-0.2}{\sqrt{0.2\cdot0.8/1000}}=3.1623
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `3.1623>1.645`, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận tỷ lệ lớn hơn 0.2.

---

## Bài 4.10

### Đề bài

`n=250`, `x=30`. Khoảng tin cậy 98%, `d=0.04`, kiểm định `H0:p=0.1`, `H1:p≠0.1`.

### Giải

```math
\hat p=\frac{30}{250}=0.12
```

Khoảng tin cậy 98%, `z=2.326`:

```math
E=2.326\sqrt{\frac{0.12\cdot0.88}{250}}=0.0478
```

```math
CI=[0.0722;0.1678]
```

Cỡ mẫu:

```math
n\ge\frac{2.326^2\cdot0.12\cdot0.88}{0.04^2}=357.11
```

Làm tròn lên: `n=358`.

Kiểm định:

```math
Z=\frac{0.12-0.1}{\sqrt{0.1\cdot0.9/250}}=1.0541
```

Kiểm định hai phía, bác bỏ nếu `|Z|>1.96`. Vì `1.0541<1.96`, không bác bỏ `H0`.

### Kết luận

Chưa đủ cơ sở để kết luận tỷ lệ khác 0.1.

---

# MỤC 5. TƯƠNG QUAN VÀ HỒI QUY TUYẾN TÍNH

## Cách suy nghĩ chung

Bài tương quan - hồi quy có 3 việc:

1. Tính hệ số tương quan `r` để xem X và Y liên hệ mạnh/yếu, thuận/nghịch.
2. Lập phương trình hồi quy tuyến tính dạng:

```math
\hat Y=a+bX
```

3. Dự đoán bằng cách thay giá trị X vào phương trình.

Quy ước nhận xét:

- `r>0`: tương quan thuận.
- `r<0`: tương quan nghịch.
- `|r|` càng gần 1 thì tương quan càng mạnh.

---

## Bài 5.1

### Đề bài

| X | Y |
|---:|---:|
| 2 | 20 |
| 3 | 25 |
| 5 | 37 |
| 6 | 42 |
| 8 | 55 |
| 9 | 60 |

Tính `r`, lập hồi quy Y theo X, dự đoán khi `X=7`.

### Giải

Sau khi tính bằng công thức hồi quy hoặc máy tính thống kê, ta được:

```math
r=0.9982
```

Vì `r` dương và rất gần 1 nên X và Y tương quan thuận rất mạnh. Chi phí quảng cáo tăng thì doanh thu có xu hướng tăng rõ.

Phương trình hồi quy:

```math
\hat Y=8.8571+5.6429X
```

Dự đoán khi `X=7`:

```math
\hat Y=8.8571+5.6429\cdot7=48.3571
```

### Kết luận

`r=0.9982`, hồi quy `Ŷ=8.8571+5.6429X`, dự đoán `Y(7)=48.3571`.

---

## Bài 5.2

### Đề bài

| X | Y |
|---:|---:|
| 1 | 4.2 |
| 2 | 5.0 |
| 3 | 5.6 |
| 4 | 6.4 |
| 5 | 7.1 |
| 6 | 7.8 |
| 7 | 8.4 |

### Giải

Kết quả tính được:

```math
r=0.9983
```

`r` dương gần 1, nên số giờ học và điểm thi có tương quan thuận rất mạnh.

Phương trình hồi quy:

```math
\hat Y=3.5714+0.6929X
```

Dự đoán khi `X=8`:

```math
\hat Y=3.5714+0.6929\cdot8=9.1143
```

### Kết luận

`r=0.9983`, `Ŷ=3.5714+0.6929X`, `Y(8)=9.1143`.

---

## Bài 5.3

### Đề bài

| X | Y |
|---:|---:|
| 20 | 120 |
| 22 | 128 |
| 24 | 135 |
| 26 | 150 |
| 28 | 165 |
| 30 | 178 |

### Giải

```math
r=0.9894
```

`r` dương và gần 1 nên nhiệt độ và điện tiêu thụ có tương quan thuận rất mạnh.

```math
\hat Y=-2.8571+5.9143X
```

Khi `X=27`:

```math
\hat Y=-2.8571+5.9143\cdot27=156.8286
```

### Kết luận

`r=0.9894`, `Ŷ=-2.8571+5.9143X`, `Y(27)=156.8286`.

---

## Bài 5.4

### Đề bài

| X | Y |
|---:|---:|
| 1 | 5 |
| 2 | 7 |
| 3 | 9 |
| 4 | 13 |
| 5 | 16 |
| 6 | 20 |

### Giải

```math
r=0.9912
```

Tuổi máy và chi phí bảo trì tương quan thuận rất mạnh.

```math
\hat Y=1.8667+2.8857X
```

Khi `X=7`:

```math
\hat Y=1.8667+2.8857\cdot7=22.0667
```

### Kết luận

`r=0.9912`, `Ŷ=1.8667+2.8857X`, `Y(7)=22.0667`.

---

## Bài 5.5

### Đề bài

| X | Y |
|---:|---:|
| 10 | 100 |
| 12 | 92 |
| 14 | 85 |
| 16 | 70 |
| 18 | 63 |
| 20 | 55 |

### Giải

```math
r=-0.9920
```

`r` âm và gần -1 nên giá bán và số lượng bán có tương quan nghịch rất mạnh. Giá tăng thì số lượng bán có xu hướng giảm.

```math
\hat Y=147.3333-4.7000X
```

Khi `X=15`:

```math
\hat Y=147.3333-4.7\cdot15=76.8333
```

### Kết luận

`r=-0.9920`, `Ŷ=147.3333-4.7000X`, `Y(15)=76.8333`.

---

## Bài 5.6

### Đề bài

| X | Y |
|---:|---:|
| 5 | 40 |
| 7 | 52 |
| 8 | 58 |
| 10 | 73 |
| 12 | 86 |
| 15 | 105 |

### Giải

```math
r=0.9991
```

Số nhân viên và sản lượng tương quan thuận rất mạnh.

```math
\hat Y=4.5513+6.6923X
```

Khi `X=11`:

```math
\hat Y=4.5513+6.6923\cdot11=78.1667
```

### Kết luận

`r=0.9991`, `Ŷ=4.5513+6.6923X`, `Y(11)=78.1667`.

---

## Bài 5.7

### Đề bài

| X | Y |
|---:|---:|
| 30 | 2.0 |
| 35 | 2.5 |
| 40 | 3.5 |
| 45 | 4.0 |
| 50 | 5.4 |
| 55 | 6.1 |

### Giải

```math
r=0.9892
```

Độ ẩm và tỷ lệ lỗi tương quan thuận rất mạnh.

```math
\hat Y=-3.0629+0.1646X
```

Khi `X=48`:

```math
\hat Y=-3.0629+0.1646\cdot48=4.8371
```

### Kết luận

`r=0.9892`, `Ŷ=-3.0629+0.1646X`, `Y(48)=4.8371`.

---

## Bài 5.8

### Đề bài

| X | Y |
|---:|---:|
| 1 | 8 |
| 2 | 13 |
| 3 | 17 |
| 4 | 22 |
| 5 | 26 |
| 6 | 31 |

### Giải

```math
r=0.9994
```

Tháng tuổi và khối lượng tương quan thuận rất mạnh.

```math
\hat Y=3.6667+4.5333X
```

Khi `X=7`:

```math
\hat Y=3.6667+4.5333\cdot7=35.4000
```

### Kết luận

`r=0.9994`, `Ŷ=3.6667+4.5333X`, `Y(7)=35.4000`.

---

## Bài 5.9

### Đề bài

| X | Y |
|---:|---:|
| 3 | 4 |
| 5 | 7 |
| 7 | 10 |
| 9 | 13 |
| 11 | 18 |
| 13 | 20 |

### Giải

```math
r=0.9949
```

Độ dài chương trình và số lỗi tương quan thuận rất mạnh.

```math
\hat Y=-1.0667+1.6464X
```

Khi `X=10`:

```math
\hat Y=-1.0667+1.6464\cdot10=15.3970
```

### Kết luận

`r=0.9949`, `Ŷ=-1.0667+1.6464X`, `Y(10)=15.3970`.

---

## Bài 5.10

### Đề bài

| X | Y |
|---:|---:|
| 1 | 9 |
| 3 | 13 |
| 4 | 15 |
| 6 | 19 |
| 8 | 25 |
| 10 | 30 |

### Giải

```math
r=0.9977
```

Kinh nghiệm và lương tương quan thuận rất mạnh.

```math
\hat Y=6.1872+2.3498X
```

Khi `X=7`:

```math
\hat Y=6.1872+2.3498\cdot7=22.6355
```

### Kết luận

`r=0.9977`, `Ŷ=6.1872+2.3498X`, `Y(7)=22.6355`.

---

# TÓM TẮT CÁCH ÁP DỤNG TRONG PHÒNG THI

## 1. Gặp bài xác suất nhiều nguồn

Vẽ cây:

```text
Nguồn → kết quả
```

Sau đó cộng các nhánh tạo ra kết quả cần tìm.

## 2. Gặp chữ “biết rằng”

Nghĩ đến xác suất có điều kiện:

```math
P(A|B)=\frac{P(A\cap B)}{P(B)}
```

Nếu có nhiều nguồn, dùng Bayes.

## 3. Gặp bài rút/chọn cùng lúc

Dùng tổ hợp:

```math
P=\frac{\text{số cách thuận lợi}}{\text{số cách tất cả}}
```

## 4. Gặp phân phối chuẩn

Luôn viết:

```math
σ=\sqrt{σ^2},\quad Z=\frac{X-μ}{σ}
```

## 5. Gặp mật độ liên tục

Không được tính kỳ vọng ngay. Phải tìm `k` trước bằng điều kiện:

```math
\int f(x)dx=1
```

## 6. Gặp ước lượng - kiểm định

Tách xem bài hỏi kỳ vọng hay tỷ lệ:

- Có `x̄, s`: kỳ vọng.
- Có `x/n`: tỷ lệ.

## 7. Gặp hồi quy

Làm theo thứ tự:

```text
Tính r → nhận xét → lập Ŷ=a+bX → thay X để dự đoán
```
