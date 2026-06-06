# MỤC 1 - BÀI GIẢI CHI TIẾT: XÁC SUẤT ĐẦY ĐỦ, BAYES, TỔ HỢP

> File này tách riêng Mục 1. Mỗi bài có **đề bài đầy đủ**, **dữ kiện**, **nhận diện dạng**, **giải từng bước**, **vì sao làm như vậy**, và **mẹo áp dụng**.

---

# Khung tư duy Mục 1

## 1. Xác suất đầy đủ

Dùng khi một kết quả có thể xảy ra từ nhiều nguồn khác nhau.

Mẫu:

```text
Nguồn H1 → kết quả A
Nguồn H2 → kết quả A
Nguồn H3 → kết quả A
```

Công thức:

```math
P(A)=P(H_1)P(A|H_1)+P(H_2)P(A|H_2)+...+P(H_n)P(A|H_n)
```

**Vì sao nhân?** Vì đi theo một nhánh cần xảy ra liên tiếp 2 việc: chọn nguồn đó và trong nguồn đó sinh ra kết quả A.

**Vì sao cộng?** Vì các nguồn loại trừ nhau: một sản phẩm không thể vừa thuộc dây chuyền A vừa thuộc dây chuyền B.

## 2. Bayes

Dùng khi biết kết quả đã xảy ra rồi hỏi ngược lại nguyên nhân.

Công thức:

```math
P(H_i|A)=\frac{P(H_i)P(A|H_i)}{P(A)}
```

Hiểu bằng lời:

```text
Mẫu số = tất cả các cách làm A xảy ra.
Tử số = riêng nhánh Hi làm A xảy ra.
```

## 3. Tổ hợp

Dùng khi rút/chọn cùng lúc, không quan tâm thứ tự.

```math
P(A)=\frac{\text{số cách thuận lợi}}{\text{số cách tất cả}}
```

---

# Bài 1.1. Dây chuyền sản xuất

## Đề bài

Một nhà máy có 3 dây chuyền A, B, C sản xuất lần lượt **40%**, **35%**, **25%** tổng sản phẩm. Tỷ lệ sản phẩm lỗi tương ứng là **3%**, **5%**, **8%**.

a. Tính xác suất chọn ngẫu nhiên được một sản phẩm bị lỗi.  
b. Biết sản phẩm được chọn bị lỗi, tính xác suất sản phẩm đó do dây chuyền C sản xuất.

## Dữ kiện

Gọi `L` là biến cố sản phẩm bị lỗi.

```math
P(A)=0.40,\quad P(B)=0.35,\quad P(C)=0.25
```

```math
P(L|A)=0.03,\quad P(L|B)=0.05,\quad P(L|C)=0.08
```

## Nhận diện dạng

Câu a hỏi xác suất sản phẩm lỗi. Lỗi có thể đến từ A, B hoặc C, nên dùng xác suất đầy đủ.

Câu b có cụm **biết sản phẩm bị lỗi**, nghĩa là đã biết kết quả `L`, hỏi ngược lại nguồn `C`, nên dùng Bayes.

## Giải từng bước

### a. Tính xác suất sản phẩm bị lỗi

Lập bảng nhánh:

| Nhánh | Xác suất vào nhánh | Xác suất lỗi trong nhánh | Xác suất nhánh lỗi |
|---|---:|---:|---:|
| A → lỗi | 0.40 | 0.03 | 0.0120 |
| B → lỗi | 0.35 | 0.05 | 0.0175 |
| C → lỗi | 0.25 | 0.08 | 0.0200 |

Sản phẩm lỗi là tổng của 3 nhánh lỗi:

```math
P(L)=0.40\cdot0.03+0.35\cdot0.05+0.25\cdot0.08
```

```math
P(L)=0.012+0.0175+0.020=0.0495
```

### b. Biết lỗi, xác suất do C

Ta cần:

```math
P(C|L)
```

Theo Bayes:

```math
P(C|L)=\frac{P(C)P(L|C)}{P(L)}
```

Tử số là nhánh `C → lỗi`:

```math
P(C)P(L|C)=0.25\cdot0.08=0.020
```

Mẫu số là toàn bộ xác suất lỗi đã tính ở câu a:

```math
P(L)=0.0495
```

```math
P(C|L)=\frac{0.020}{0.0495}=0.4040
```

## Kết luận

```text
a/ 0.0495
b/ 0.4040
```

## Mẹo áp dụng

Câu a đi xuôi: nguồn → kết quả. Câu b đi ngược: kết quả → nguồn. Đi ngược thì dùng Bayes.

---

# Bài 1.2. Chọn hộp rồi rút bi

## Đề bài

Có 3 hộp I, II, III được chọn với xác suất lần lượt **0.30**, **0.50**, **0.20**. Tỷ lệ bi đỏ trong các hộp I, II, III lần lượt là **70%**, **40%**, **20%**. Chọn ngẫu nhiên 1 hộp rồi rút 1 viên bi.

a. Tính xác suất rút được bi đỏ.  
b. Biết đã rút được bi đỏ, tính xác suất viên bi đó được rút từ hộp I.

## Dữ kiện

Gọi `Đ` là biến cố rút được bi đỏ.

```math
P(I)=0.30,\quad P(II)=0.50,\quad P(III)=0.20
```

```math
P(Đ|I)=0.70,\quad P(Đ|II)=0.40,\quad P(Đ|III)=0.20
```

## Nhận diện dạng

Có 2 tầng: chọn hộp trước, rồi rút bi trong hộp đó. Bi đỏ có thể đến từ 3 hộp, nên câu a dùng xác suất đầy đủ. Câu b biết đã đỏ, hỏi hộp I, nên dùng Bayes.

## Giải từng bước

### a. Xác suất rút được bi đỏ

| Nhánh | P(chọn hộp) | P(đỏ nếu chọn hộp) | Tích |
|---|---:|---:|---:|
| I → đỏ | 0.30 | 0.70 | 0.2100 |
| II → đỏ | 0.50 | 0.40 | 0.2000 |
| III → đỏ | 0.20 | 0.20 | 0.0400 |

```math
P(Đ)=0.30\cdot0.70+0.50\cdot0.40+0.20\cdot0.20
```

```math
P(Đ)=0.21+0.20+0.04=0.4500
```

### b. Biết đỏ, xác suất từ hộp I

Tử số là nhánh `I → đỏ`:

```math
P(I\cap Đ)=P(I)P(Đ|I)=0.30\cdot0.70=0.21
```

Mẫu số là tất cả nhánh tạo ra đỏ:

```math
P(Đ)=0.45
```

```math
P(I|Đ)=\frac{0.21}{0.45}=0.4667
```

## Kết luận

```text
a/ 0.4500
b/ 0.4667
```

---

# Bài 1.3. Xét nghiệm bệnh

## Đề bài

Một bệnh có tỷ lệ mắc trong cộng đồng là **1%**. Một loại xét nghiệm có xác suất cho kết quả dương tính nếu người đó thật sự mắc bệnh là **95%**. Nếu người đó không mắc bệnh, xác suất xét nghiệm vẫn cho dương tính giả là **4%**.

a. Tính xác suất một người được chọn ngẫu nhiên có kết quả xét nghiệm dương tính.  
b. Biết kết quả xét nghiệm là dương tính, tính xác suất người đó thật sự mắc bệnh.

## Dữ kiện

```text
B = mắc bệnh
K = không mắc bệnh
+ = xét nghiệm dương tính
```

```math
P(B)=0.01,\quad P(K)=0.99
```

```math
P(+|B)=0.95,\quad P(+|K)=0.04
```

## Nhận diện dạng

Dương tính có thể là dương tính thật hoặc dương tính giả. Câu a dùng xác suất đầy đủ. Câu b hỏi ngược từ dương tính về mắc bệnh, nên dùng Bayes.

## Giải từng bước

### a. Xác suất dương tính

| Nhánh | Xác suất nhóm | Xác suất dương tính | Xác suất nhánh |
|---|---:|---:|---:|
| Bệnh → dương tính | 0.01 | 0.95 | 0.0095 |
| Không bệnh → dương tính giả | 0.99 | 0.04 | 0.0396 |

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

## Vì sao không phải 95%?

`95%` là xác suất dương tính nếu đã biết người đó bệnh. Nhưng câu b hỏi ngược: đã dương tính thì xác suất bệnh là bao nhiêu. Hai xác suất này khác nhau.

Do bệnh hiếm, nhóm không bệnh rất lớn. Vì vậy dương tính giả từ nhóm không bệnh vẫn chiếm phần lớn trong tổng số kết quả dương tính.

## Kết luận

```text
a/ 0.0491
b/ 0.1935
```

---

# Bài 1.4. Hai xạ thủ

## Đề bài

Hai xạ thủ A và B bắn độc lập vào cùng một mục tiêu. Xác suất bắn trúng của A là **0.75**, của B là **0.60**.

a. Tính xác suất cả hai xạ thủ cùng bắn trúng.  
b. Biết chỉ có đúng 1 viên đạn trúng mục tiêu, tính xác suất viên đạn trúng là của A.

## Dữ kiện

```math
P(A)=0.75,\quad P(A^c)=0.25
```

```math
P(B)=0.60,\quad P(B^c)=0.40
```

## Nhận diện dạng

Đề nói độc lập nên xác suất cùng xảy ra bằng tích. Câu b có điều kiện “biết đúng 1 viên trúng”, nên phải thu hẹp không gian mẫu về các trường hợp đúng 1 viên trúng.

## Giải từng bước

### a. Cả hai cùng trúng

```math
P(A\cap B)=P(A)P(B)=0.75\cdot0.60=0.4500
```

### b. Biết đúng 1 viên trúng

Đúng 1 viên trúng gồm 2 trường hợp:

| Trường hợp | Xác suất |
|---|---:|
| A trúng, B trật | `0.75×0.40=0.30` |
| A trật, B trúng | `0.25×0.60=0.15` |

```math
P(\text{đúng 1})=0.30+0.15=0.45
```

Viên trúng là của A tương ứng nhánh A trúng, B trật:

```math
P(A\text{ trúng}|\text{đúng 1})=\frac{0.30}{0.45}=0.6667
```

## Kết luận

```text
a/ 0.4500
b/ 0.6667
```

---

# Bài 1.5. Rút bài

## Đề bài

Rút ngẫu nhiên 5 lá bài từ bộ bài chuẩn 52 lá.

a. Tính xác suất có ít nhất 1 lá Ách.  
b. Tính xác suất có đúng 2 lá Ách.

## Dữ kiện

```text
4 lá Ách
48 lá không Ách
Tổng 52 lá
Rút 5 lá cùng lúc
```

## Nhận diện dạng

Rút cùng lúc nên không xét thứ tự, dùng tổ hợp. Tổng số cách rút 5 lá:

```math
C_{52}^{5}
```

## Giải từng bước

### a. Ít nhất 1 lá Ách

“Ít nhất 1” gồm 1, 2, 3, 4 lá Ách. Cộng trực tiếp dài. Dùng biến cố đối:

```text
Ít nhất 1 Ách = 1 - không có Ách nào
```

Không có Ách: chọn 5 lá từ 48 lá không Ách.

```math
P=1-\frac{C_{48}^{5}}{C_{52}^{5}}=0.3412
```

### b. Đúng 2 lá Ách

Đúng 2 Ách nghĩa là 2 lá thuộc nhóm Ách, 3 lá còn lại không thuộc nhóm Ách.

```math
P=\frac{C_4^2C_{48}^{3}}{C_{52}^{5}}=0.0399
```

## Kết luận

```text
a/ 0.3412
b/ 0.0399
```

---

# Bài 1.6. Rút bi cùng lúc

## Đề bài

Một hộp có **8 bi xanh** và **12 bi đỏ**. Lấy ngẫu nhiên cùng lúc 4 viên bi.

a. Tính xác suất lấy được đúng 2 bi xanh.  
b. Tính xác suất lấy được ít nhất 2 bi xanh.

## Dữ kiện và nhận diện

Tổng có `20` bi. Lấy cùng lúc nên dùng tổ hợp. Tổng số cách:

```math
C_{20}^{4}
```

## Giải từng bước

### a. Đúng 2 bi xanh

```math
P=\frac{C_8^2C_{12}^2}{C_{20}^{4}}=0.3814
```

### b. Ít nhất 2 bi xanh

Các trường hợp:

```text
2 xanh, 2 đỏ
3 xanh, 1 đỏ
4 xanh, 0 đỏ
```

```math
P=\frac{C_8^2C_{12}^2+C_8^3C_{12}^{1}+C_8^4}{C_{20}^{4}}=0.4696
```

## Kết luận

```text
a/ 0.3814
b/ 0.4696
```

---

# Bài 1.7. Sinh viên đậu môn học

## Đề bài

Một lớp có **25%** sinh viên năm nhất, **45%** sinh viên năm hai và **30%** sinh viên năm ba. Tỷ lệ đậu môn X của ba nhóm tương ứng là **80%**, **60%**, **30%**.

a. Tính xác suất sinh viên đó đậu môn X.  
b. Biết sinh viên đó đậu môn X, tính xác suất sinh viên đó thuộc năm hai.

## Giải từng bước

Gọi `D` là biến cố đậu.

| Nhóm | Tỷ lệ nhóm | Tỷ lệ đậu | Tích |
|---|---:|---:|---:|
| Năm nhất | 0.25 | 0.80 | 0.20 |
| Năm hai | 0.45 | 0.60 | 0.27 |
| Năm ba | 0.30 | 0.30 | 0.09 |

```math
P(D)=0.20+0.27+0.09=0.5600
```

```math
P(\text{năm hai}|D)=\frac{0.27}{0.56}=0.4821
```

## Kết luận

```text
a/ 0.5600
b/ 0.4821
```

---

# Bài 1.8. Chuyển bi giữa hai hộp

## Đề bài

Hộp A có **5 bi đỏ**, **3 bi xanh**. Hộp B có **4 bi đỏ**, **6 bi xanh**. Rút ngẫu nhiên 1 viên bi từ hộp A chuyển sang hộp B, sau đó rút ngẫu nhiên 1 viên bi từ hộp B.

a. Tính xác suất rút ở hộp B được bi đỏ.  
b. Biết rút ở hộp B được bi đỏ, tính xác suất viên bi chuyển từ hộp A sang hộp B là bi xanh.

## Giải từng bước

Hộp B thay đổi theo màu bi chuyển từ A.

| Trường hợp | Xác suất chuyển | B sau chuyển | Xác suất rút đỏ |
|---|---:|---|---:|
| Chuyển đỏ | `5/8` | 5 đỏ, 6 xanh | `5/11` |
| Chuyển xanh | `3/8` | 4 đỏ, 7 xanh | `4/11` |

### a. Xác suất rút đỏ ở B

```math
P(Đ_B)=\frac58\cdot\frac5{11}+\frac38\cdot\frac4{11}=0.4205
```

### b. Biết rút đỏ ở B, xác suất chuyển xanh

```math
P(\text{chuyển xanh}|Đ_B)=\frac{\frac38\cdot\frac4{11}}{0.4205}=0.3243
```

## Kết luận

```text
a/ 0.4205
b/ 0.3243
```

---

# Bài 1.9. Tỷ lệ mắc bệnh theo giới tính

## Đề bài

Một vùng dân cư có **55% nữ** và **45% nam**. Tỷ lệ mắc bệnh M ở nữ là **20%**, ở nam là **10%**.

a. Tính xác suất người đó mắc bệnh M.  
b. Biết người đó mắc bệnh M, tính xác suất người đó là nam.

## Giải từng bước

```math
P(M)=0.55\cdot0.20+0.45\cdot0.10=0.1550
```

```math
P(\text{nam}|M)=\frac{0.45\cdot0.10}{0.155}=0.2903
```

## Kết luận

```text
a/ 0.1550
b/ 0.2903
```

---

# Bài 1.10. Tung xu rồi rút bi

## Đề bài

Tung một đồng xu cân đối. Nếu đồng xu ra **sấp**, bỏ vào bình 1 bi đỏ và 2 bi vàng. Nếu đồng xu ra **ngửa**, bỏ vào bình 2 bi đỏ và 2 bi vàng. Sau đó rút ngẫu nhiên 1 viên bi từ bình.

a. Tính xác suất rút được bi đỏ.  
b. Biết rút được bi đỏ, tính xác suất đồng xu đã ra ngửa.

## Giải từng bước

| Nhánh | Xác suất xu | Xác suất đỏ | Tích |
|---|---:|---:|---:|
| Sấp → đỏ | `1/2` | `1/3` | `1/6` |
| Ngửa → đỏ | `1/2` | `2/4` | `1/4` |

```math
P(Đ)=\frac16+\frac14=0.4167
```

```math
P(\text{ngửa}|Đ)=\frac{\frac12\cdot\frac24}{0.4167}=0.6000
```

## Kết luận

```text
a/ 0.4167
b/ 0.6000
```
