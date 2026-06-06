# BÀI GIẢI CHI TIẾT XÁC SUẤT - THỐNG KÊ

> File bài giải này được viết để **mapping 1-1 với file bài tập** `Bai_tap_XSTK_theo_cau_truc_50_bai.md`.  
> Mỗi bài giữ đúng số thứ tự, đúng nội dung đề, đúng các ý a/b/c/d... rồi mới giải chi tiết.

---

## Quy ước chung

- `C(n,k)` là tổ hợp: chọn `k` phần tử từ `n` phần tử, không xét thứ tự.
- Nếu `X ~ N(μ, σ²)` thì tham số thứ hai là **phương sai**, độ lệch chuẩn là `σ = √σ²`.
- Kết quả xác suất làm tròn 4 chữ số nếu không yêu cầu khác.
- Khi gặp “biết rằng ...” thường dùng xác suất có điều kiện hoặc Bayes.
- Khi gặp “rút cùng lúc”, “chọn”, “lấy đồng thời” thường dùng tổ hợp.

---

# MỤC 1. XÁC SUẤT CHƯƠNG 1

## Bài 1.1. Dây chuyền sản xuất

### Đề bài

Một nhà máy có 3 dây chuyền A, B, C sản xuất lần lượt **40%**, **35%**, **25%** tổng sản phẩm. Tỷ lệ sản phẩm lỗi tương ứng là **3%**, **5%**, **8%**.

Yêu cầu:

a. Tính xác suất chọn ngẫu nhiên được một sản phẩm bị lỗi.  
b. Biết sản phẩm được chọn bị lỗi, tính xác suất sản phẩm đó do dây chuyền C sản xuất.

### Nhận diện dạng bài

Một sản phẩm lỗi có thể đến từ nhiều nguồn khác nhau: A, B hoặc C. Vì vậy câu a dùng **công thức xác suất đầy đủ**. Câu b đã biết sản phẩm bị lỗi rồi hỏi ngược lại nó thuộc nguồn nào, nên dùng **Bayes**.

### Cách suy nghĩ

Muốn sản phẩm bị lỗi thì có 3 đường:

```text
A sản xuất → A làm lỗi
B sản xuất → B làm lỗi
C sản xuất → C làm lỗi
```

Ba đường này tách biệt nhau nên cộng lại.

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

```math
P(C|L)=\frac{P(C)P(L|C)}{P(L)}=\frac{0.25\cdot0.08}{0.0495}=0.4040
```

### Kết luận

- a. Xác suất sản phẩm bị lỗi là `0.0495`.
- b. Nếu biết sản phẩm bị lỗi, xác suất sản phẩm đó do dây chuyền C sản xuất là `0.4040`.

---

## Bài 1.2. Chọn hộp rồi rút bi

### Đề bài

Có 3 hộp I, II, III được chọn với xác suất lần lượt **0,30**, **0,50**, **0,20**. Tỷ lệ bi đỏ trong các hộp I, II, III lần lượt là **70%**, **40%**, **20%**.

Chọn ngẫu nhiên 1 hộp, sau đó rút ngẫu nhiên 1 viên bi.

Yêu cầu:

a. Tính xác suất rút được bi đỏ.  
b. Biết đã rút được bi đỏ, tính xác suất viên bi đó được rút từ hộp I.

### Nhận diện dạng bài

Kết quả “rút được đỏ” phụ thuộc vào việc chọn hộp nào trước. Đây là xác suất đầy đủ. Câu b hỏi ngược từ kết quả đỏ về hộp I nên dùng Bayes.

### Giải

Gọi `Đ` là biến cố rút được bi đỏ.

```math
P(Đ)=0.30\cdot0.70+0.50\cdot0.40+0.20\cdot0.20
```

```math
P(Đ)=0.21+0.20+0.04=0.4500
```

Biết đã rút được đỏ, xác suất hộp được chọn là I:

```math
P(I|Đ)=\frac{P(I)P(Đ|I)}{P(Đ)}=\frac{0.30\cdot0.70}{0.45}=0.4667
```

### Kết luận

- a. `P(Đ)=0.4500`.
- b. `P(I|Đ)=0.4667`.

---

## Bài 1.3. Xét nghiệm bệnh

### Đề bài

Một bệnh có tỷ lệ mắc trong cộng đồng là **1%**. Một loại xét nghiệm có xác suất cho kết quả dương tính nếu người đó thật sự mắc bệnh là **95%**. Nếu người đó không mắc bệnh, xác suất xét nghiệm vẫn cho dương tính giả là **4%**.

Yêu cầu:

a. Tính xác suất một người được chọn ngẫu nhiên có kết quả xét nghiệm dương tính.  
b. Biết kết quả xét nghiệm là dương tính, tính xác suất người đó thật sự mắc bệnh.

### Nhận diện dạng bài

Có 2 nhóm người: mắc bệnh và không mắc bệnh. Dương tính có thể là dương tính thật hoặc dương tính giả. Câu a dùng xác suất đầy đủ, câu b dùng Bayes.

### Giải

Gọi:

- `B`: người đó mắc bệnh.
- `K`: người đó không mắc bệnh.
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
P(B|+)=\frac{P(B)P(+|B)}{P(+)}=\frac{0.01\cdot0.95}{0.0491}=0.1935
```

### Giải thích vì sao kết quả không cao

Dù xét nghiệm đúng với người bệnh tới 95%, bệnh chỉ có tỷ lệ 1%. Nhóm không bệnh rất lớn, nên 4% dương tính giả từ nhóm này vẫn tạo ra nhiều trường hợp dương tính.

### Kết luận

- a. Xác suất dương tính là `0.0491`.
- b. Nếu dương tính, xác suất thật sự mắc bệnh là `0.1935`.

---

## Bài 1.4. Hai xạ thủ

### Đề bài

Hai xạ thủ A và B bắn độc lập vào cùng một mục tiêu. Xác suất bắn trúng của A là **0,75**, của B là **0,60**.

Yêu cầu:

a. Tính xác suất cả hai xạ thủ cùng bắn trúng.  
b. Biết chỉ có đúng 1 viên đạn trúng mục tiêu, tính xác suất viên đạn trúng là của A.

### Nhận diện dạng bài

Hai người bắn độc lập, nên xác suất cùng xảy ra bằng tích. Câu b là xác suất có điều kiện trên biến cố “đúng 1 viên trúng”.

### Giải

Gọi `A` là A trúng, `B` là B trúng.

Câu a:

```math
P(A\cap B)=P(A)P(B)=0.75\cdot0.60=0.4500
```

Câu b:

Biến cố “đúng 1 viên trúng” gồm 2 trường hợp:

```text
A trúng, B trật
A trật, B trúng
```

```math
P(\text{đúng 1 trúng})=0.75\cdot0.40+0.25\cdot0.60=0.30+0.15=0.45
```

Biến cố cần hỏi là “A trúng, B trật”:

```math
P(A\text{ trúng và B trật})=0.75\cdot0.40=0.30
```

Do đó:

```math
P(A\text{ trúng}|\text{đúng 1 trúng})=\frac{0.30}{0.45}=0.6667
```

### Kết luận

- a. `0.4500`.
- b. `0.6667`.

---

## Bài 1.5. Rút bài

### Đề bài

Rút ngẫu nhiên 5 lá bài từ bộ bài chuẩn 52 lá.

Yêu cầu:

a. Tính xác suất có ít nhất 1 lá Ách.  
b. Tính xác suất có đúng 2 lá Ách.

### Nhận diện dạng bài

Rút 5 lá cùng lúc nên thứ tự không quan trọng, dùng tổ hợp. Bộ bài có 4 lá Ách và 48 lá không phải Ách.

### Giải

Tổng số cách rút 5 lá:

```math
C_{52}^{5}
```

Câu a:

“Ít nhất 1 Ách” gồm 1, 2, 3 hoặc 4 Ách. Cộng trực tiếp được nhưng dài. Dùng biến cố đối nhanh hơn.

Biến cố đối của “ít nhất 1 Ách” là “không có Ách”.

```math
P(\text{ít nhất 1 Ách})=1-P(\text{không có Ách})
```

```math
P=1-\frac{C_{48}^{5}}{C_{52}^{5}}=0.3412
```

Câu b:

Đúng 2 Ách nghĩa là:

- Chọn 2 lá từ 4 lá Ách.
- Chọn 3 lá còn lại từ 48 lá không Ách.

```math
P=\frac{C_4^2C_{48}^{3}}{C_{52}^{5}}=0.0399
```

### Kết luận

- a. `0.3412`.
- b. `0.0399`.

---

## Bài 1.6. Rút bi cùng lúc

### Đề bài

Một hộp có **8 bi xanh** và **12 bi đỏ**. Lấy ngẫu nhiên cùng lúc 4 viên bi.

Yêu cầu:

a. Tính xác suất lấy được đúng 2 bi xanh.  
b. Tính xác suất lấy được ít nhất 2 bi xanh.

### Nhận diện dạng bài

Lấy cùng lúc 4 bi nên thứ tự không quan trọng. Dùng tổ hợp.

### Giải

Tổng số bi là 20. Tổng số cách lấy 4 bi:

```math
C_{20}^{4}
```

Câu a:

Đúng 2 bi xanh nghĩa là chọn 2 từ 8 bi xanh và 2 từ 12 bi đỏ.

```math
P=\frac{C_8^2C_{12}^2}{C_{20}^{4}}=0.3814
```

Câu b:

Ít nhất 2 bi xanh gồm:

```text
2 xanh, 2 đỏ
3 xanh, 1 đỏ
4 xanh, 0 đỏ
```

```math
P=\frac{C_8^2C_{12}^2+C_8^3C_{12}^{1}+C_8^4}{C_{20}^{4}}=0.4696
```

### Kết luận

- a. `0.3814`.
- b. `0.4696`.

---

## Bài 1.7. Sinh viên đậu môn học

### Đề bài

Một lớp có **25%** sinh viên năm nhất, **45%** sinh viên năm hai và **30%** sinh viên năm ba. Tỷ lệ đậu môn X của ba nhóm tương ứng là **80%**, **60%**, **30%**.

Chọn ngẫu nhiên một sinh viên trong lớp.

Yêu cầu:

a. Tính xác suất sinh viên đó đậu môn X.  
b. Biết sinh viên đó đậu môn X, tính xác suất sinh viên đó thuộc năm hai.

### Nhận diện dạng bài

Sinh viên đậu có thể đến từ 3 nhóm năm học. Câu a dùng xác suất đầy đủ. Câu b có dữ kiện “biết đậu” nên dùng Bayes.

### Giải

Gọi `D` là biến cố sinh viên đậu môn X.

```math
P(D)=0.25\cdot0.80+0.45\cdot0.60+0.30\cdot0.30
```

```math
P(D)=0.20+0.27+0.09=0.5600
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

Hộp A có **5 bi đỏ**, **3 bi xanh**. Hộp B có **4 bi đỏ**, **6 bi xanh**. Rút ngẫu nhiên 1 viên bi từ hộp A chuyển sang hộp B, sau đó rút ngẫu nhiên 1 viên bi từ hộp B.

Yêu cầu:

a. Tính xác suất rút ở hộp B được bi đỏ.  
b. Biết rút ở hộp B được bi đỏ, tính xác suất viên bi chuyển từ hộp A sang hộp B là bi xanh.

### Nhận diện dạng bài

Kết quả rút ở B phụ thuộc vào màu bi đã chuyển từ A sang B. Phải chia thành 2 nhánh: chuyển đỏ hoặc chuyển xanh.

### Giải

Nếu chuyển đỏ từ A:

```math
P(\text{chuyển đỏ})=\frac58
```

Khi đó B có 5 đỏ, 6 xanh, tổng 11 bi:

```math
P(\text{rút đỏ từ B}|\text{chuyển đỏ})=\frac5{11}
```

Nếu chuyển xanh từ A:

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

Biết đã rút đỏ ở B, hỏi khả năng nhánh ban đầu là chuyển xanh:

```math
P(\text{chuyển xanh}|Đ_B)=\frac{\frac38\cdot\frac4{11}}{0.4205}=0.3243
```

### Kết luận

- a. `0.4205`.
- b. `0.3243`.

---

## Bài 1.9. Tỷ lệ mắc bệnh theo giới tính

### Đề bài

Một vùng dân cư có **55% nữ** và **45% nam**. Tỷ lệ mắc bệnh M ở nữ là **20%**, ở nam là **10%**.

Chọn ngẫu nhiên 1 người trong vùng.

Yêu cầu:

a. Tính xác suất người đó mắc bệnh M.  
b. Biết người đó mắc bệnh M, tính xác suất người đó là nam.

### Nhận diện dạng bài

Người mắc bệnh có thể thuộc nhóm nữ hoặc nam. Câu a là xác suất đầy đủ, câu b là Bayes.

### Giải

Gọi `M` là biến cố mắc bệnh.

```math
P(M)=0.55\cdot0.20+0.45\cdot0.10
```

```math
P(M)=0.11+0.045=0.1550
```

Biết người đó mắc bệnh, xác suất là nam:

```math
P(\text{nam}|M)=\frac{0.45\cdot0.10}{0.155}=0.2903
```

### Kết luận

- a. `0.1550`.
- b. `0.2903`.

---

## Bài 1.10. Tung xu rồi rút bi

### Đề bài

Tung một đồng xu cân đối. Nếu đồng xu ra **sấp**, bỏ vào bình 1 bi đỏ và 2 bi vàng. Nếu đồng xu ra **ngửa**, bỏ vào bình 2 bi đỏ và 2 bi vàng. Sau đó rút ngẫu nhiên 1 viên bi từ bình.

Yêu cầu:

a. Tính xác suất rút được bi đỏ.  
b. Biết rút được bi đỏ, tính xác suất đồng xu đã ra ngửa.

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

# MỤC 2. BIẾN NGẪU NHIÊN LIÊN TỤC PHÂN PHỐI CHUẨN

## Quy trình chung

Với `X ~ N(μ, σ²)`, luôn làm theo 3 bước:

```text
Bước 1: Lấy σ = căn bậc hai của phương sai.
Bước 2: Chuẩn hóa Z = (X - μ) / σ.
Bước 3: Dùng bảng chuẩn hoặc máy tính để lấy xác suất/phân vị.
```

---

## Bài 2.1

### Đề bài

Cho biến ngẫu nhiên `X ~ N(60, 64)`.

Yêu cầu:

a. Tính `P(50 < X < 70)`.  
b. Tìm `T` sao cho `P(X < T) = 0,90`.

### Giải

Vì `X ~ N(60,64)` nên:

```math
\mu=60,\quad \sigma=\sqrt{64}=8
```

Câu a:

```math
P(50<X<70)=P\left(\frac{50-60}{8}<Z<\frac{70-60}{8}\right)
```

```math
=P(-1.25<Z<1.25)=0.7887
```

Câu b:

`P(X<T)=0.90` tương ứng `z_0.90=1.2816`.

```math
T=\mu+\sigma z=60+8\cdot1.2816=70.2524
```

### Kết luận

- a. `0.7887`.
- b. `T=70.2524`.

---

## Bài 2.2

### Đề bài

Cho biến ngẫu nhiên `X ~ N(100, 225)`.

Yêu cầu:

a. Tính `P(85 < X < 120)`.  
b. Tìm `T` sao cho `P(X < T) = 0,95`.

### Giải

```math
\mu=100,\quad \sigma=\sqrt{225}=15
```

Câu a:

```math
P(85<X<120)=P\left(\frac{85-100}{15}<Z<\frac{120-100}{15}\right)
```

```math
=P(-1<Z<1.3333)=0.7501
```

Câu b:

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

Cho biến ngẫu nhiên `X ~ N(500, 1600)`.

Yêu cầu:

a. Tính `P(450 < X < 560)`.  
b. Tìm `T` sao cho `P(X < T) = 0,10`.

### Giải

```math
\mu=500,\quad \sigma=\sqrt{1600}=40
```

Câu a:

```math
P(450<X<560)=P\left(\frac{450-500}{40}<Z<\frac{560-500}{40}\right)
```

```math
=P(-1.25<Z<1.5)=0.8275
```

Câu b:

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

Cho biến ngẫu nhiên `X ~ N(170, 36)`.

Yêu cầu:

a. Tính `P(160 < X < 180)`.  
b. Tìm `T` sao cho `P(X > T) = 0,80`.

### Giải

```math
\mu=170,\quad \sigma=\sqrt{36}=6
```

Câu a:

```math
P(160<X<180)=P\left(\frac{160-170}{6}<Z<\frac{180-170}{6}\right)
```

```math
=P(-1.6667<Z<1.6667)=0.9044
```

Câu b:

Đề cho xác suất bên phải:

```math
P(X>T)=0.80
```

Đổi về xác suất bên trái:

```math
P(X<T)=1-0.80=0.20
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

Cho biến ngẫu nhiên `X ~ N(30, 16)`.

Yêu cầu:

a. Tính `P(25 < X < 35)`.  
b. Tìm `T` sao cho `P(X > T) = 0,05`.

### Giải

```math
\mu=30,\quad \sigma=\sqrt{16}=4
```

Câu a:

```math
P(25<X<35)=P(-1.25<Z<1.25)=0.7887
```

Câu b:

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

Cho biến ngẫu nhiên `X ~ N(75, 100)`.

Yêu cầu:

a. Tính `P(65 < X < 90)`.  
b. Tìm `T` sao cho `P(X < T) = 0,975`.

### Giải

```math
\mu=75,\quad \sigma=\sqrt{100}=10
```

Câu a:

```math
P(65<X<90)=P\left(\frac{65-75}{10}<Z<\frac{90-75}{10}\right)
```

```math
=P(-1<Z<1.5)=0.7745
```

Câu b:

```math
z_{0.975}=1.9600
```

```math
T=75+10\cdot1.9600=94.6000
```

### Kết luận

- a. `0.7745`.
- b. `T=94.6000`.

---

## Bài 2.7

### Đề bài

Cho biến ngẫu nhiên `X ~ N(12, 6.25)`.

Yêu cầu:

a. Tính `P(9 < X < 15)`.  
b. Tìm `T` sao cho `P(X < T) = 0,20`.

### Giải

```math
\mu=12,\quad \sigma=\sqrt{6.25}=2.5
```

Câu a:

```math
P(9<X<15)=P\left(\frac{9-12}{2.5}<Z<\frac{15-12}{2.5}\right)
```

```math
=P(-1.2<Z<1.2)=0.7699
```

Câu b:

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

Cho biến ngẫu nhiên `X ~ N(200, 625)`.

Yêu cầu:

a. Tính `P(180 < X < 230)`.  
b. Tìm `T` sao cho `P(X > T) = 0,85`.

### Giải

```math
\mu=200,\quad \sigma=\sqrt{625}=25
```

Câu a:

```math
P(180<X<230)=P\left(\frac{180-200}{25}<Z<\frac{230-200}{25}\right)
```

```math
=P(-0.8<Z<1.2)=0.6731
```

Câu b:

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

Cho biến ngẫu nhiên `X ~ N(3.5, 0.16)`.

Yêu cầu:

a. Tính `P(3.0 < X < 4.1)`.  
b. Tìm `T` sao cho `P(X < T) = 0,99`.

### Giải

```math
\mu=3.5,\quad \sigma=\sqrt{0.16}=0.4
```

Câu a:

```math
P(3.0<X<4.1)=P\left(\frac{3.0-3.5}{0.4}<Z<\frac{4.1-3.5}{0.4}\right)
```

```math
=P(-1.25<Z<1.5)=0.8275
```

Câu b:

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

Cho biến ngẫu nhiên `X ~ N(1000, 14400)`.

Yêu cầu:

a. Tính `P(850 < X < 1100)`.  
b. Tìm `T` sao cho `P(X > T) = 0,15`.

### Giải

```math
\mu=1000,\quad \sigma=\sqrt{14400}=120
```

Câu a:

```math
P(850<X<1100)=P\left(\frac{850-1000}{120}<Z<\frac{1100-1000}{120}\right)
```

```math
=P(-1.25<Z<0.8333)=0.6915
```

Câu b:

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

Với mật độ `f(x)=kg(x)` trên khoảng `(a,b)`, làm đúng thứ tự:

1. Tìm `k` từ điều kiện `∫f(x)dx=1`.
2. Tính `E(X)=∫xf(x)dx`.
3. Tính `E(X²)=∫x²f(x)dx`.
4. Tính `Var(X)=E(X²)-[E(X)]²`.
5. Tính xác suất bằng tích phân trên khoảng đề yêu cầu.

---

## Bài 3.1

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=kx,\quad 0<x<2.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(0.5 < X < 1.5)`.

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
P(0.5<X<1.5)=\int_{0.5}^{1.5}0.5x\,dx=0.5000
```

### Kết luận

`k=0.5`, `E(X)=1.3333`, `Var(X)=0.2222`, xác suất `0.5000`.

---

## Bài 3.2

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=kx^2,\quad 0<x<3.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1 < X < 2)`.

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
E(X)=\int_0^3x\cdot\frac19x^2dx=\frac19\int_0^3x^3dx=2.2500
```

Moment bậc hai:

```math
E(X^2)=\frac19\int_0^3x^4dx=5.4000
```

Phương sai:

```math
Var(X)=5.4000-2.2500^2=0.3375
```

Xác suất:

```math
P(1<X<2)=\int_1^2\frac19x^2dx=0.2593
```

### Kết luận

`k=0.1111`, `E(X)=2.2500`, `Var(X)=0.3375`, xác suất `0.2593`.

---

## Bài 3.3

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k(x+1),\quad 0<x<2.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(0.5 < X < 1.5)`.

### Giải

```math
\int_0^2k(x+1)dx=1
```

```math
k\left[\frac{x^2}{2}+x\right]_0^2=1\Rightarrow 4k=1\Rightarrow k=0.25
```

```math
E(X)=\int_0^2x\cdot0.25(x+1)dx=1.1667
```

```math
E(X^2)=\int_0^2x^2\cdot0.25(x+1)dx=1.6667
```

```math
Var(X)=1.6667-1.1667^2=0.3056
```

```math
P(0.5<X<1.5)=\int_{0.5}^{1.5}0.25(x+1)dx=0.5000
```

### Kết luận

`k=0.25`, `E(X)=1.1667`, `Var(X)=0.3056`, xác suất `0.5000`.

---

## Bài 3.4

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k(4-x),\quad 0<x<4.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1 < X < 3)`.

### Giải

```math
\int_0^4k(4-x)dx=1
```

```math
k\left[4x-\frac{x^2}{2}\right]_0^4=1\Rightarrow 8k=1\Rightarrow k=0.125
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

### Kết luận

`k=0.125`, `E(X)=1.3333`, `Var(X)=0.8889`, xác suất `0.5000`.

---

## Bài 3.5

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=\frac{k}{x^2},\quad 1<x<3.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1.5 < X < 2.5)`.

### Giải

```math
\int_1^3\frac{k}{x^2}dx=1
```

```math
k\left[-\frac1x\right]_1^3=1\Rightarrow k\left(1-\frac13\right)=1
```

```math
k\cdot\frac23=1\Rightarrow k=1.5
```

```math
E(X)=\int_1^3x\cdot\frac{1.5}{x^2}dx=1.5\int_1^3\frac1xdx=1.5\ln3=1.6479
```

```math
E(X^2)=\int_1^3x^2\cdot\frac{1.5}{x^2}dx=1.5\int_1^3dx=3
```

```math
Var(X)=3-1.6479^2=0.2827
```

```math
P(1.5<X<2.5)=\int_{1.5}^{2.5}\frac{1.5}{x^2}dx=0.4000
```

### Kết luận

`k=1.5`, `E(X)=1.6479`, `Var(X)=0.2827`, xác suất `0.4000`.

---

## Bài 3.6

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k\sin x,\quad 0<x<\pi.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(π/6 < X < π/2)`.

### Giải

```math
\int_0^\pi k\sin xdx=1
```

```math
k[-\cos x]_0^\pi=1\Rightarrow 2k=1\Rightarrow k=0.5
```

```math
E(X)=\int_0^\pi x\cdot0.5\sin xdx=1.5708
```

Hàm mật độ đối xứng quanh `π/2`, nên kỳ vọng nằm tại `π/2`.

```math
E(X^2)=\int_0^\pi x^2\cdot0.5\sin xdx=2.9348
```

```math
Var(X)=2.9348-1.5708^2=0.4674
```

```math
P(\pi/6<X<\pi/2)=\int_{\pi/6}^{\pi/2}0.5\sin xdx=0.4330
```

### Kết luận

`k=0.5`, `E(X)=1.5708`, `Var(X)=0.4674`, xác suất `0.4330`.

---

## Bài 3.7

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k(1-x^2),\quad -1<x<1.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(-0.5 < X < 0.5)`.

### Giải

```math
\int_{-1}^{1}k(1-x^2)dx=1
```

```math
k\left[x-\frac{x^3}{3}\right]_{-1}^{1}=1\Rightarrow k\cdot\frac43=1\Rightarrow k=0.75
```

Vì miền `(-1,1)` đối xứng và mật độ cũng đối xứng nên:

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

### Kết luận

`k=0.75`, `E(X)=0`, `Var(X)=0.2`, xác suất `0.6875`.

---

## Bài 3.8

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=k(2x+1),\quad 0<x<1.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(0.25 < X < 0.75)`.

### Giải

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

### Kết luận

`k=0.5`, `E(X)=0.5833`, `Var(X)=0.0764`, xác suất `0.5000`.

---

## Bài 3.9

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=ke^{-x/2},\quad x>0.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1 < X < 4)`.

### Giải

```math
\int_0^{+\infty}ke^{-x/2}dx=1
```

```math
\int_0^{+\infty}e^{-x/2}dx=2
```

```math
2k=1\Rightarrow k=0.5
```

Đây là phân phối mũ với tham số `λ=0.5`, nên:

```math
E(X)=\frac1λ=2
```

```math
Var(X)=\frac1{λ^2}=4
```

```math
P(1<X<4)=\int_1^40.5e^{-x/2}dx=e^{-1/2}-e^{-2}=0.4712
```

### Kết luận

`k=0.5`, `E(X)=2`, `Var(X)=4`, xác suất `0.4712`.

---

## Bài 3.10

### Đề bài

Cho BNN liên tục X có hàm mật độ:

```math
f(x)=kxe^{-x},\quad x>0.
```

Yêu cầu:

a. Tìm `k`.  
b. Tính `E(X)` và `Var(X)`.  
c. Tính `P(1 < X < 3)`.

### Giải

```math
\int_0^{+\infty}kxe^{-x}dx=1
```

```math
\int_0^{+\infty}xe^{-x}dx=1\Rightarrow k=1
```

```math
E(X)=\int_0^{+\infty}x\cdot xe^{-x}dx=\int_0^{+\infty}x^2e^{-x}dx=2
```

```math
E(X^2)=\int_0^{+\infty}x^2\cdot xe^{-x}dx=\int_0^{+\infty}x^3e^{-x}dx=6
```

```math
Var(X)=6-2^2=2
```

```math
P(1<X<3)=\int_1^3xe^{-x}dx=0.5768
```

### Kết luận

`k=1`, `E(X)=2`, `Var(X)=2`, xác suất `0.5768`.

---

# MỤC 4. ƯỚC LƯỢNG VÀ KIỂM ĐỊNH THỐNG KÊ

## Công thức chung

Khoảng tin cậy kỳ vọng:

```math
\bar x\pm z\frac{s}{\sqrt n}
```

Khoảng tin cậy tỷ lệ:

```math
\hat p\pm z\sqrt{\frac{\hat p(1-\hat p)}{n}}
```

Cỡ mẫu cho kỳ vọng:

```math
n\ge\left(\frac{zs}{d}\right)^2
```

Cỡ mẫu cho tỷ lệ:

```math
n\ge\frac{z^2\hat p(1-\hat p)}{d^2}
```

---

## Bài 4.1. Trung bình chiều cao

### Đề bài

Khảo sát 64 quan sát về chiều cao, thu được:

- `n = 64`
- `x̄ = 168.5`
- `s = 7.2`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 95% cho kỳ vọng.  
c. Với độ chính xác `d = 1.5`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 170`, `H1: μ < 170`.

### Giải

Câu a:

```math
\hat\mu=\bar x=168.5
```

Câu b, với 95% thì `z=1.96`:

```math
E=1.96\cdot\frac{7.2}{\sqrt{64}}=1.764
```

```math
CI=168.5\pm1.764=[166.736;170.264]
```

Câu c:

```math
n\ge\left(\frac{1.96\cdot7.2}{1.5}\right)^2=88.47
```

Làm tròn lên: `n=89`.

Câu d:

```math
Z=\frac{168.5-170}{7.2/\sqrt{64}}=-1.6667
```

Vì `H1: μ<170`, bác bỏ nếu `Z<-1.645`. Ta có `-1.6667<-1.645`, nên bác bỏ `H0`.

### Kết luận

- a. `168.5`.
- b. `[166.736;170.264]`.
- c. `n=89`.
- d. Có đủ cơ sở để kết luận `μ<170`.

---

## Bài 4.2. Thời gian xử lý

### Đề bài

Khảo sát 36 quan sát về thời gian xử lý, thu được:

- `n = 36`
- `x̄ = 12.4`
- `s = 2.1`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 99% cho kỳ vọng.  
c. Với độ chính xác `d = 0.8`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 13`, `H1: μ ≠ 13`.

### Giải

```math
\hat\mu=12.4
```

Với 99%, `z=2.576`:

```math
E=2.576\cdot\frac{2.1}{\sqrt{36}}=0.9016
```

```math
CI=[12.4-0.9016;12.4+0.9016]=[11.4984;13.3016]
```

```math
n\ge\left(\frac{2.576\cdot2.1}{0.8}\right)^2=45.69
```

Làm tròn lên: `n=46`.

```math
Z=\frac{12.4-13}{2.1/\sqrt{36}}=-1.7143
```

Vì `H1: μ≠13`, bác bỏ nếu `|Z|>1.96`. Ở đây `1.7143<1.96`, nên không bác bỏ `H0`.

### Kết luận

- a. `12.4`.
- b. `[11.4984;13.3016]`.
- c. `n=46`.
- d. Chưa đủ cơ sở để kết luận `μ≠13`.

---

## Bài 4.3. Điểm thi

### Đề bài

Khảo sát 100 quan sát về điểm thi, thu được:

- `n = 100`
- `x̄ = 7.1`
- `s = 1.3`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 90% cho kỳ vọng.  
c. Với độ chính xác `d = 0.25`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 7.0`, `H1: μ > 7.0`.

### Giải

```math
\hat\mu=7.1
```

Với 90%, `z=1.645`:

```math
E=1.645\cdot\frac{1.3}{\sqrt{100}}=0.2139
```

```math
CI=[7.1-0.2139;7.1+0.2139]=[6.8861;7.3139]
```

```math
n\ge\left(\frac{1.645\cdot1.3}{0.25}\right)^2=73.18
```

Làm tròn lên: `n=74`.

```math
Z=\frac{7.1-7.0}{1.3/\sqrt{100}}=0.7692
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `0.7692<1.645`, không bác bỏ `H0`.

### Kết luận

- a. `7.1`.
- b. `[6.8861;7.3139]`.
- c. `n=74`.
- d. Chưa đủ cơ sở để kết luận `μ>7.0`.

---

## Bài 4.4. Khối lượng sản phẩm

### Đề bài

Khảo sát 49 quan sát về khối lượng, thu được:

- `n = 49`
- `x̄ = 50.8`
- `s = 4.5`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 95% cho kỳ vọng.  
c. Với độ chính xác `d = 1.0`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 52`, `H1: μ < 52`.

### Giải

```math
\hat\mu=50.8
```

```math
E=1.96\cdot\frac{4.5}{\sqrt{49}}=1.26
```

```math
CI=[50.8-1.26;50.8+1.26]=[49.5400;52.0600]
```

```math
n\ge\left(\frac{1.96\cdot4.5}{1.0}\right)^2=77.79
```

Làm tròn lên: `n=78`.

```math
Z=\frac{50.8-52}{4.5/\sqrt{49}}=-1.8667
```

Kiểm định trái, bác bỏ nếu `Z<-1.645`. Vì `-1.8667<-1.645`, bác bỏ `H0`.

### Kết luận

- a. `50.8`.
- b. `[49.5400;52.0600]`.
- c. `n=78`.
- d. Có đủ cơ sở để kết luận `μ<52`.

---

## Bài 4.5. Tuổi thọ pin

### Đề bài

Khảo sát 81 quan sát về tuổi thọ pin, thu được:

- `n = 81`
- `x̄ = 9.6`
- `s = 1.8`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 98% cho kỳ vọng.  
c. Với độ chính xác `d = 0.5`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 9.2`, `H1: μ > 9.2`.

### Giải

```math
\hat\mu=9.6
```

Với 98%, `z=2.326`:

```math
E=2.326\cdot\frac{1.8}{\sqrt{81}}=0.4652
```

```math
CI=[9.6-0.4652;9.6+0.4652]=[9.1348;10.0652]
```

```math
n\ge\left(\frac{2.326\cdot1.8}{0.5}\right)^2=70.13
```

Làm tròn lên: `n=71`.

```math
Z=\frac{9.6-9.2}{1.8/\sqrt{81}}=2.0000
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `2.0000>1.645`, bác bỏ `H0`.

### Kết luận

- a. `9.6`.
- b. `[9.1348;10.0652]`.
- c. `n=71`.
- d. Có đủ cơ sở để kết luận `μ>9.2`.

---

## Bài 4.6. Tỷ lệ sản phẩm loại A

### Đề bài

Khảo sát 400 sản phẩm, có 52 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 95% cho tỷ lệ.  
c. Với độ chính xác `d = 0.03`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.1`, `H1: p > 0.1`.

### Giải

```math
\hat p=\frac{52}{400}=0.1300
```

Với 95%, `z=1.96`:

```math
E=1.96\sqrt{\frac{0.13(1-0.13)}{400}}=0.0330
```

```math
CI=[0.13-0.0330;0.13+0.0330]=[0.0970;0.1630]
```

```math
n\ge\frac{1.96^2\cdot0.13\cdot0.87}{0.03^2}=482.84
```

Làm tròn lên: `n=483`.

```math
Z=\frac{0.13-0.1}{\sqrt{0.1(1-0.1)/400}}=2.0000
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `2.0000>1.645`, bác bỏ `H0`.

### Kết luận

- a. `p̂=0.1300`.
- b. `[0.0970;0.1630]`.
- c. `n=483`.
- d. Có đủ cơ sở để kết luận `p>0.1`.

---

## Bài 4.7. Tỷ lệ lỗi khảo sát 625 mẫu

### Đề bài

Khảo sát 625 sản phẩm, có 75 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 99% cho tỷ lệ.  
c. Với độ chính xác `d = 0.025`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.15`, `H1: p < 0.15`.

### Giải

```math
\hat p=\frac{75}{625}=0.1200
```

Với 99%, `z=2.576`:

```math
E=2.576\sqrt{\frac{0.12\cdot0.88}{625}}=0.0335
```

```math
CI=[0.0865;0.1535]
```

```math
n\ge\frac{2.576^2\cdot0.12\cdot0.88}{0.025^2}=1120.82
```

Làm tròn lên: `n=1121`.

```math
Z=\frac{0.12-0.15}{\sqrt{0.15\cdot0.85/625}}=-2.1004
```

Kiểm định trái, bác bỏ nếu `Z<-1.645`. Vì `-2.1004<-1.645`, bác bỏ `H0`.

### Kết luận

- a. `p̂=0.1200`.
- b. `[0.0865;0.1535]`.
- c. `n=1121`.
- d. Có đủ cơ sở để kết luận `p<0.15`.

---

## Bài 4.8. Khảo sát 300 mẫu

### Đề bài

Khảo sát 300 sản phẩm, có 138 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 90% cho tỷ lệ.  
c. Với độ chính xác `d = 0.05`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.5`, `H1: p ≠ 0.5`.

### Giải

```math
\hat p=\frac{138}{300}=0.4600
```

Với 90%, `z=1.645`:

```math
E=1.645\sqrt{\frac{0.46\cdot0.54}{300}}=0.0473
```

```math
CI=[0.4127;0.5073]
```

```math
n\ge\frac{1.645^2\cdot0.46\cdot0.54}{0.05^2}=268.89
```

Làm tròn lên: `n=269`.

```math
Z=\frac{0.46-0.5}{\sqrt{0.5\cdot0.5/300}}=-1.3856
```

Kiểm định hai phía, bác bỏ nếu `|Z|>1.96`. Vì `1.3856<1.96`, không bác bỏ `H0`.

### Kết luận

- a. `p̂=0.4600`.
- b. `[0.4127;0.5073]`.
- c. `n=269`.
- d. Chưa đủ cơ sở để kết luận `p≠0.5`.

---

## Bài 4.9. Khảo sát 1000 mẫu

### Đề bài

Khảo sát 1000 sản phẩm, có 240 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 95% cho tỷ lệ.  
c. Với độ chính xác `d = 0.02`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.2`, `H1: p > 0.2`.

### Giải

```math
\hat p=\frac{240}{1000}=0.2400
```

Với 95%, `z=1.96`:

```math
E=1.96\sqrt{\frac{0.24\cdot0.76}{1000}}=0.0265
```

```math
CI=[0.2135;0.2665]
```

```math
n\ge\frac{1.96^2\cdot0.24\cdot0.76}{0.02^2}=1751.77
```

Làm tròn lên: `n=1752`.

```math
Z=\frac{0.24-0.2}{\sqrt{0.2\cdot0.8/1000}}=3.1623
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `3.1623>1.645`, bác bỏ `H0`.

### Kết luận

- a. `p̂=0.2400`.
- b. `[0.2135;0.2665]`.
- c. `n=1752`.
- d. Có đủ cơ sở để kết luận `p>0.2`.

---

## Bài 4.10. Khảo sát 250 mẫu

### Đề bài

Khảo sát 250 sản phẩm, có 30 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 98% cho tỷ lệ.  
c. Với độ chính xác `d = 0.04`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.1`, `H1: p ≠ 0.1`.

### Giải

```math
\hat p=\frac{30}{250}=0.1200
```

Với 98%, `z=2.326`:

```math
E=2.326\sqrt{\frac{0.12\cdot0.88}{250}}=0.0478
```

```math
CI=[0.0722;0.1678]
```

```math
n\ge\frac{2.326^2\cdot0.12\cdot0.88}{0.04^2}=357.11
```

Làm tròn lên: `n=358`.

```math
Z=\frac{0.12-0.1}{\sqrt{0.1\cdot0.9/250}}=1.0541
```

Kiểm định hai phía, bác bỏ nếu `|Z|>1.96`. Vì `1.0541<1.96`, không bác bỏ `H0`.

### Kết luận

- a. `p̂=0.1200`.
- b. `[0.0722;0.1678]`.
- c. `n=358`.
- d. Chưa đủ cơ sở để kết luận `p≠0.1`.

---

# MỤC 5. TƯƠNG QUAN VÀ HỒI QUY TUYẾN TÍNH

## Quy trình chung

Mỗi bài hồi quy làm theo 3 bước:

1. Tính hệ số tương quan `r`.
2. Lập phương trình hồi quy `Ŷ=a+bX`.
3. Thay giá trị X cần dự đoán vào phương trình.

Nhận xét nhanh:

- `r>0`: tương quan thuận.
- `r<0`: tương quan nghịch.
- `|r|` gần 1: tương quan mạnh.

---

## Bài 5.1. Quảng cáo và doanh thu

### Đề bài

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

### Giải

Kết quả tính được:

```math
r=0.9982
```

Vì `r` dương và rất gần 1 nên X và Y tương quan thuận rất mạnh.

Phương trình hồi quy:

```math
\hat Y=8.8571+5.6429X
```

Dự đoán khi `X=7`:

```math
\hat Y=8.8571+5.6429\cdot7=48.3571
```

### Kết luận

- a. `r=0.9982`, tương quan thuận rất mạnh.
- b. `Ŷ=8.8571+5.6429X`.
- c. `Y(7)=48.3571`.

---

## Bài 5.2. Giờ học và điểm thi

### Đề bài

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

### Giải

```math
r=0.9983
```

`r` dương gần 1, nên số giờ học và điểm thi có tương quan thuận rất mạnh.

```math
\hat Y=3.5714+0.6929X
```

```math
\hat Y(8)=3.5714+0.6929\cdot8=9.1143
```

### Kết luận

- a. `r=0.9983`, tương quan thuận rất mạnh.
- b. `Ŷ=3.5714+0.6929X`.
- c. `Y(8)=9.1143`.

---

## Bài 5.3. Nhiệt độ và lượng điện tiêu thụ

### Đề bài

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

### Giải

```math
r=0.9894
```

`r` dương và gần 1 nên nhiệt độ và lượng điện tiêu thụ có tương quan thuận rất mạnh.

```math
\hat Y=-2.8571+5.9143X
```

```math
\hat Y(27)=-2.8571+5.9143\cdot27=156.8286
```

### Kết luận

- a. `r=0.9894`, tương quan thuận rất mạnh.
- b. `Ŷ=-2.8571+5.9143X`.
- c. `Y(27)=156.8286`.

---

## Bài 5.4. Tuổi máy và chi phí bảo trì

### Đề bài

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

### Giải

```math
r=0.9912
```

Tuổi máy và chi phí bảo trì tương quan thuận rất mạnh.

```math
\hat Y=1.8667+2.8857X
```

```math
\hat Y(7)=1.8667+2.8857\cdot7=22.0667
```

### Kết luận

- a. `r=0.9912`, tương quan thuận rất mạnh.
- b. `Ŷ=1.8667+2.8857X`.
- c. `Y(7)=22.0667`.

---

## Bài 5.5. Giá bán và số lượng bán

### Đề bài

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

### Giải

```math
r=-0.9920
```

`r` âm và gần -1, nên giá bán và số lượng bán có tương quan nghịch rất mạnh.

```math
\hat Y=147.3333-4.7000X
```

```math
\hat Y(15)=147.3333-4.7\cdot15=76.8333
```

### Kết luận

- a. `r=-0.9920`, tương quan nghịch rất mạnh.
- b. `Ŷ=147.3333-4.7000X`.
- c. `Y(15)=76.8333`.

---

## Bài 5.6. Nhân viên và sản lượng

### Đề bài

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

### Giải

```math
r=0.9991
```

Số nhân viên và sản lượng tương quan thuận rất mạnh.

```math
\hat Y=4.5513+6.6923X
```

```math
\hat Y(11)=4.5513+6.6923\cdot11=78.1667
```

### Kết luận

- a. `r=0.9991`, tương quan thuận rất mạnh.
- b. `Ŷ=4.5513+6.6923X`.
- c. `Y(11)=78.1667`.

---

## Bài 5.7. Độ ẩm và tỷ lệ lỗi

### Đề bài

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

### Giải

```math
r=0.9892
```

Độ ẩm và tỷ lệ lỗi tương quan thuận rất mạnh.

```math
\hat Y=-3.0629+0.1646X
```

```math
\hat Y(48)=-3.0629+0.1646\cdot48=4.8371
```

### Kết luận

- a. `r=0.9892`, tương quan thuận rất mạnh.
- b. `Ŷ=-3.0629+0.1646X`.
- c. `Y(48)=4.8371`.

---

## Bài 5.8. Tháng tuổi và khối lượng

### Đề bài

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

### Giải

```math
r=0.9994
```

Tháng tuổi và khối lượng tương quan thuận rất mạnh.

```math
\hat Y=3.6667+4.5333X
```

```math
\hat Y(7)=3.6667+4.5333\cdot7=35.4000
```

### Kết luận

- a. `r=0.9994`, tương quan thuận rất mạnh.
- b. `Ŷ=3.6667+4.5333X`.
- c. `Y(7)=35.4000`.

---

## Bài 5.9. Độ dài chương trình và số lỗi

### Đề bài

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

### Giải

```math
r=0.9949
```

Độ dài chương trình và số lỗi tương quan thuận rất mạnh.

```math
\hat Y=-1.0667+1.6464X
```

```math
\hat Y(10)=-1.0667+1.6464\cdot10=15.3970
```

### Kết luận

- a. `r=0.9949`, tương quan thuận rất mạnh.
- b. `Ŷ=-1.0667+1.6464X`.
- c. `Y(10)=15.3970`.

---

## Bài 5.10. Kinh nghiệm và lương

### Đề bài

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

### Giải

```math
r=0.9977
```

Kinh nghiệm và lương tương quan thuận rất mạnh.

```math
\hat Y=6.1872+2.3498X
```

```math
\hat Y(7)=6.1872+2.3498\cdot7=22.6355
```

### Kết luận

- a. `r=0.9977`, tương quan thuận rất mạnh.
- b. `Ŷ=6.1872+2.3498X`.
- c. `Y(7)=22.6355`.

---

# TÓM TẮT CÁCH ÁP DỤNG TRONG PHÒNG THI

## 1. Bài nhiều nguồn

Dùng cây xác suất:

```text
Nguồn → kết quả
```

Cộng tất cả nhánh tạo ra kết quả cần tìm.

## 2. Bài có “biết rằng”

Dùng:

```math
P(A|B)=\frac{P(A\cap B)}{P(B)}
```

Nếu hỏi ngược nguồn, dùng Bayes.

## 3. Bài rút/chọn cùng lúc

Dùng:

```math
P=\frac{\text{số cách thuận lợi}}{\text{số cách tất cả}}
```

## 4. Bài phân phối chuẩn

Luôn viết trước:

```math
\sigma=\sqrt{\sigma^2},\quad Z=\frac{X-\mu}{\sigma}
```

## 5. Bài mật độ liên tục

Phải tìm `k` trước, rồi mới tính kỳ vọng/phương sai/xác suất.

## 6. Bài ước lượng - kiểm định

- Có `x̄, s`: bài kỳ vọng.
- Có `x/n`: bài tỷ lệ.

## 7. Bài hồi quy

Thứ tự làm:

```text
Tính r → nhận xét → lập Ŷ=a+bX → thay X để dự đoán
```
