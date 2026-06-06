# BÀI GIẢI SIÊU CHI TIẾT XÁC SUẤT - THỐNG KÊ 50 BÀI

> File mới viết theo phong cách bài giảng: **Gọi biến cố → Lọc dữ kiện → Lập mô hình → Tách trường hợp → Thay số → Giải thích vì sao → Kết luận**.  
> Mục tiêu: người mất gốc đọc vào biết cách làm lại bài tương tự trong phòng thi.

---

# CÁCH DÙNG FILE NÀY

Mỗi bài được trình bày theo 7 lớp:

1. **Đề bài**: chép rõ đề, giữ mapping 1-1 với file bài tập.
2. **Dữ kiện cần lấy**: chỉ ra số nào dùng ở đâu.
3. **Nhận diện dạng**: giải thích vì sao bài thuộc dạng đó.
4. **Ý tưởng làm bài**: trước khi tính phải biết mình đang làm gì.
5. **Giải từng bước**: viết công thức, thay số, tính kết quả.
6. **Giải thích vì sao**: nêu lý do chọn công thức/cách tách trường hợp.
7. **Mẹo phòng thi**: gặp bài tương tự thì xử lý nhanh thế nào.

---

# MỤC 1. XÁC SUẤT CHƯƠNG 1

## Khung tư duy Mục 1

### 1. Khi nào dùng xác suất đầy đủ?

Dùng khi một kết quả có thể xảy ra qua nhiều **nguồn/nhánh** khác nhau.

Mẫu tư duy:

```text
Nguồn 1 → kết quả A
Nguồn 2 → kết quả A
Nguồn 3 → kết quả A
```

Khi đó:

```math
P(A)=P(H_1)P(A|H_1)+P(H_2)P(A|H_2)+...+P(H_n)P(A|H_n)
```

### 2. Khi nào dùng Bayes?

Dùng khi đề có kiểu:

```text
Biết kết quả A đã xảy ra, hỏi nguyên nhân/nguồn là gì?
```

Công thức:

```math
P(H_i|A)=\frac{P(H_i)P(A|H_i)}{P(A)}
```

Hiểu cực đơn giản:

```text
Mẫu số = tất cả cách tạo ra A
Tử số = riêng cách vừa thuộc Hi vừa tạo ra A
```

### 3. Khi nào dùng tổ hợp?

Dùng khi đề có các từ:

```text
rút cùng lúc, chọn ra, lấy đồng thời, không xét thứ tự
```

Công thức xác suất cổ điển:

```math
P(A)=\frac{|A|}{|\Omega|}
```

---

## Bài 1.1. Dây chuyền sản xuất

### Đề bài

Một nhà máy có 3 dây chuyền A, B, C sản xuất lần lượt **40%**, **35%**, **25%** tổng sản phẩm. Tỷ lệ sản phẩm lỗi tương ứng là **3%**, **5%**, **8%**.

Yêu cầu:

a. Tính xác suất chọn ngẫu nhiên được một sản phẩm bị lỗi.  
b. Biết sản phẩm được chọn bị lỗi, tính xác suất sản phẩm đó do dây chuyền C sản xuất.

### Dữ kiện cần lấy

```text
P(A)=0.40, P(B)=0.35, P(C)=0.25
P(L|A)=0.03, P(L|B)=0.05, P(L|C)=0.08
```

Trong đó `L` là biến cố “sản phẩm bị lỗi”.

### Nhận diện dạng

Sản phẩm lỗi có thể đến từ 3 dây chuyền. Một kết quả `Lỗi` được tạo bởi nhiều nguồn khác nhau, nên câu a dùng **xác suất đầy đủ**.

Câu b có chữ “biết sản phẩm bị lỗi”, nghĩa là đã biết kết quả, hỏi ngược nguồn C. Đây là **Bayes**.

### Ý tưởng làm bài

Ta vẽ cây:

| Nhánh | Xác suất chọn dây chuyền | Xác suất lỗi trong nhánh | Xác suất nhánh tạo ra lỗi |
|---|---:|---:|---:|
| A → lỗi | 0.40 | 0.03 | `0.40×0.03=0.012` |
| B → lỗi | 0.35 | 0.05 | `0.35×0.05=0.0175` |
| C → lỗi | 0.25 | 0.08 | `0.25×0.08=0.020` |

### Giải từng bước

#### a. Tính xác suất sản phẩm bị lỗi

```math
P(L)=P(A)P(L|A)+P(B)P(L|B)+P(C)P(L|C)
```

```math
P(L)=0.40\times0.03+0.35\times0.05+0.25\times0.08
```

```math
P(L)=0.012+0.0175+0.020=0.0495
```

#### b. Biết lỗi, xác suất do C sản xuất

Ta cần:

```math
P(C|L)
```

Theo Bayes:

```math
P(C|L)=\frac{P(C)P(L|C)}{P(L)}
```

```math
P(C|L)=\frac{0.25\times0.08}{0.0495}=\frac{0.020}{0.0495}=0.4040
```

### Giải thích vì sao

Câu b không hỏi xác suất “C và lỗi” đơn thuần. Nó hỏi **trong số những sản phẩm đã lỗi**, bao nhiêu phần đến từ C. Vì vậy phải lấy nhánh `C→lỗi` chia cho tổng tất cả nhánh lỗi.

### Kết luận

```text
a/ P(L)=0.0495 = 4.95%
b/ P(C|L)=0.4040 = 40.40%
```

### Mẹo phòng thi

Gặp câu “biết rằng sản phẩm đã lỗi” thì mẫu số gần như luôn là xác suất lỗi đã tính ở câu trước.

---

## Bài 1.2. Chọn hộp rồi rút bi

### Đề bài

Có 3 hộp I, II, III được chọn với xác suất lần lượt **0.30**, **0.50**, **0.20**. Tỷ lệ bi đỏ trong các hộp I, II, III lần lượt là **70%**, **40%**, **20%**. Chọn ngẫu nhiên 1 hộp rồi rút 1 viên bi.

Yêu cầu:

a. Tính xác suất rút được bi đỏ.  
b. Biết đã rút được bi đỏ, tính xác suất viên bi đó được rút từ hộp I.

### Dữ kiện cần lấy

```text
P(I)=0.30, P(II)=0.50, P(III)=0.20
P(Đ|I)=0.70, P(Đ|II)=0.40, P(Đ|III)=0.20
```

### Nhận diện dạng

Kết quả “rút được đỏ” phụ thuộc vào việc chọn hộp nào trước. Đây là mô hình 2 tầng:

```text
Chọn hộp → rút bi
```

Câu a dùng xác suất đầy đủ. Câu b dùng Bayes.

### Bảng nhánh

| Nhánh | Xác suất chọn hộp | Xác suất đỏ trong hộp | Xác suất nhánh đỏ |
|---|---:|---:|---:|
| I → đỏ | 0.30 | 0.70 | 0.2100 |
| II → đỏ | 0.50 | 0.40 | 0.2000 |
| III → đỏ | 0.20 | 0.20 | 0.0400 |

### Giải từng bước

#### a. Xác suất rút được đỏ

```math
P(Đ)=0.30\times0.70+0.50\times0.40+0.20\times0.20
```

```math
P(Đ)=0.21+0.20+0.04=0.45
```

#### b. Biết đỏ, xác suất từ hộp I

```math
P(I|Đ)=\frac{P(I)P(Đ|I)}{P(Đ)}
```

```math
P(I|Đ)=\frac{0.30\times0.70}{0.45}=\frac{0.21}{0.45}=0.4667
```

### Giải thích vì sao

Nếu đã rút được bi đỏ, ta không xét toàn bộ các lần rút nữa. Ta chỉ xét nhóm các lần rút ra đỏ. Trong nhóm đó, nhánh từ hộp I chiếm `0.21`, tổng nhóm đỏ là `0.45`, nên lấy `0.21/0.45`.

### Kết luận

```text
a/ 0.4500
b/ 0.4667
```

---

## Bài 1.3. Xét nghiệm bệnh

### Đề bài

Một bệnh có tỷ lệ mắc trong cộng đồng là **1%**. Một loại xét nghiệm có xác suất cho kết quả dương tính nếu người đó thật sự mắc bệnh là **95%**. Nếu người đó không mắc bệnh, xác suất xét nghiệm vẫn cho dương tính giả là **4%**.

Yêu cầu:

a. Tính xác suất một người được chọn ngẫu nhiên có kết quả xét nghiệm dương tính.  
b. Biết kết quả xét nghiệm là dương tính, tính xác suất người đó thật sự mắc bệnh.

### Dữ kiện cần lấy

```text
P(B)=0.01
P(K)=0.99
P(+|B)=0.95
P(+|K)=0.04
```

Trong đó:

```text
B = mắc bệnh
K = không mắc bệnh
+ = xét nghiệm dương tính
```

### Nhận diện dạng

Dương tính có 2 nguồn:

```text
Mắc bệnh thật → dương tính thật
Không mắc bệnh → dương tính giả
```

Câu a là xác suất đầy đủ. Câu b là Bayes.

### Bảng nhánh

| Nhánh | Xác suất nhóm | Xác suất dương tính | Xác suất nhánh dương tính |
|---|---:|---:|---:|
| Bệnh → dương tính | 0.01 | 0.95 | 0.0095 |
| Không bệnh → dương tính giả | 0.99 | 0.04 | 0.0396 |

### Giải từng bước

#### a. Xác suất xét nghiệm dương tính

```math
P(+)=P(B)P(+|B)+P(K)P(+|K)
```

```math
P(+)=0.01\times0.95+0.99\times0.04
```

```math
P(+)=0.0095+0.0396=0.0491
```

#### b. Biết dương tính, xác suất thật sự mắc bệnh

```math
P(B|+)=\frac{P(B)P(+|B)}{P(+)}
```

```math
P(B|+)=\frac{0.01\times0.95}{0.0491}=0.1935
```

### Giải thích vì sao kết quả thấp

Dù xét nghiệm đúng 95% với người bệnh, bệnh chỉ chiếm 1% cộng đồng. Nhóm không bệnh chiếm 99%, nên 4% dương tính giả từ nhóm này vẫn tạo ra số lượng dương tính giả lớn.

### Kết luận

```text
a/ P(+)=0.0491
b/ P(B|+)=0.1935
```

### Mẹo phòng thi

Bài xét nghiệm luôn phải cảnh giác với **dương tính giả**. Không được kết luận “test dương tính thì 95% mắc bệnh”.

---

## Bài 1.4. Hai xạ thủ

### Đề bài

Hai xạ thủ A và B bắn độc lập vào cùng một mục tiêu. Xác suất bắn trúng của A là **0.75**, của B là **0.60**.

Yêu cầu:

a. Tính xác suất cả hai xạ thủ cùng bắn trúng.  
b. Biết chỉ có đúng 1 viên đạn trúng mục tiêu, tính xác suất viên đạn trúng là của A.

### Dữ kiện cần lấy

```text
P(A trúng)=0.75 => P(A trật)=0.25
P(B trúng)=0.60 => P(B trật)=0.40
```

### Nhận diện dạng

Đề ghi “bắn độc lập”, nên xác suất hai biến cố cùng xảy ra bằng tích xác suất.

Câu b là xác suất có điều kiện vì đề nói “biết chỉ có đúng 1 viên trúng”.

### Giải từng bước

#### a. Cả hai cùng trúng

```math
P(A\cap B)=P(A)P(B)=0.75\times0.60=0.45
```

#### b. Đúng 1 viên trúng, xác suất viên trúng là của A

Biến cố “đúng 1 viên trúng” gồm 2 trường hợp:

| Trường hợp | A | B | Xác suất |
|---:|---|---|---:|
| 1 | Trúng | Trật | `0.75×0.40=0.30` |
| 2 | Trật | Trúng | `0.25×0.60=0.15` |

Tổng xác suất đúng 1 viên trúng:

```math
P(\text{đúng 1})=0.30+0.15=0.45
```

Trong biến cố đúng 1 viên trúng, viên trúng là của A tương ứng trường hợp 1:

```math
P(A\text{ trúng}|\text{đúng 1})=\frac{0.30}{0.45}=0.6667
```

### Giải thích vì sao

Không được lấy luôn `0.75`. Vì đã có điều kiện “đúng 1 viên trúng”, không gian mẫu bị thu hẹp còn 2 trường hợp: A trúng B trật hoặc A trật B trúng.

### Kết luận

```text
a/ 0.4500
b/ 0.6667
```

---

## Bài 1.5. Rút bài

### Đề bài

Rút ngẫu nhiên 5 lá bài từ bộ bài chuẩn 52 lá.

Yêu cầu:

a. Tính xác suất có ít nhất 1 lá Ách.  
b. Tính xác suất có đúng 2 lá Ách.

### Dữ kiện cần lấy

```text
Bộ bài có 52 lá
Có 4 lá Ách
Có 48 lá không Ách
Rút 5 lá cùng lúc
```

### Nhận diện dạng

Rút cùng lúc nên thứ tự không quan trọng. Dùng tổ hợp.

Tổng số cách rút 5 lá:

```math
|\Omega|=C_{52}^{5}
```

### Giải từng bước

#### a. Ít nhất 1 lá Ách

“Ít nhất 1” gồm 1, 2, 3, 4 lá Ách. Cộng trực tiếp dài. Dùng biến cố đối:

```text
Ít nhất 1 Ách = 1 - không có Ách nào
```

Không có Ách nghĩa là chọn 5 lá từ 48 lá không Ách:

```math
P(\text{không Ách})=\frac{C_{48}^{5}}{C_{52}^{5}}
```

Vậy:

```math
P(\text{ít nhất 1 Ách})=1-\frac{C_{48}^{5}}{C_{52}^{5}}=0.3412
```

#### b. Đúng 2 lá Ách

Bảng tách nhóm:

| Nhóm | Cần chọn | Có tất cả | Số cách |
|---|---:|---:|---:|
| Ách | 2 | 4 | `C_4^2` |
| Không Ách | 3 | 48 | `C_48^3` |

```math
P=\frac{C_4^2C_{48}^{3}}{C_{52}^{5}}=0.0399
```

### Giải thích vì sao

Dùng tổ hợp vì rút ra 5 lá không phân biệt thứ tự rút. Bộ `{A cơ, 2 rô}` giống `{2 rô, A cơ}`.

### Kết luận

```text
a/ 0.3412
b/ 0.0399
```

---

## Bài 1.6. Rút bi cùng lúc

### Đề bài

Một hộp có **8 bi xanh** và **12 bi đỏ**. Lấy ngẫu nhiên cùng lúc 4 viên bi.

Yêu cầu:

a. Tính xác suất lấy được đúng 2 bi xanh.  
b. Tính xác suất lấy được ít nhất 2 bi xanh.

### Dữ kiện cần lấy

```text
8 xanh, 12 đỏ, tổng 20 bi
Lấy cùng lúc 4 bi
```

Tổng số cách lấy:

```math
|\Omega|=C_{20}^{4}
```

### Giải từng bước

#### a. Đúng 2 bi xanh

Đúng 2 xanh thì còn lại 2 đỏ.

| Nhóm | Cần chọn | Có tất cả | Số cách |
|---|---:|---:|---:|
| Xanh | 2 | 8 | `C_8^2` |
| Đỏ | 2 | 12 | `C_12^2` |

```math
P=\frac{C_8^2C_{12}^2}{C_{20}^{4}}=0.3814
```

#### b. Ít nhất 2 bi xanh

Liệt kê đủ các trường hợp:

| Trường hợp | Số xanh | Số đỏ | Số cách |
|---:|---:|---:|---:|
| 1 | 2 | 2 | `C_8^2C_12^2` |
| 2 | 3 | 1 | `C_8^3C_12^1` |
| 3 | 4 | 0 | `C_8^4` |

```math
P=\frac{C_8^2C_{12}^2+C_8^3C_{12}^{1}+C_8^4}{C_{20}^{4}}=0.4696
```

### Giải thích vì sao

“Ít nhất 2” nghĩa là từ 2 trở lên. Vì tổng lấy 4 viên nên chỉ có thể là 2, 3 hoặc 4 bi xanh.

### Kết luận

```text
a/ 0.3814
b/ 0.4696
```

---

## Bài 1.7. Sinh viên đậu môn học

### Đề bài

Một lớp có **25%** sinh viên năm nhất, **45%** sinh viên năm hai và **30%** sinh viên năm ba. Tỷ lệ đậu môn X của ba nhóm tương ứng là **80%**, **60%**, **30%**.

Chọn ngẫu nhiên một sinh viên trong lớp.

Yêu cầu:

a. Tính xác suất sinh viên đó đậu môn X.  
b. Biết sinh viên đó đậu môn X, tính xác suất sinh viên đó thuộc năm hai.

### Dữ kiện cần lấy

```text
P(N1)=0.25, P(N2)=0.45, P(N3)=0.30
P(D|N1)=0.80, P(D|N2)=0.60, P(D|N3)=0.30
```

### Giải từng bước

Gọi `D` là biến cố sinh viên đậu môn X.

#### a. Xác suất đậu

| Nhánh | Xác suất nhóm | Xác suất đậu | Tích |
|---|---:|---:|---:|
| Năm nhất → đậu | 0.25 | 0.80 | 0.20 |
| Năm hai → đậu | 0.45 | 0.60 | 0.27 |
| Năm ba → đậu | 0.30 | 0.30 | 0.09 |

```math
P(D)=0.20+0.27+0.09=0.56
```

#### b. Biết đậu, xác suất thuộc năm hai

```math
P(N2|D)=\frac{P(N2)P(D|N2)}{P(D)}=\frac{0.45\times0.60}{0.56}=0.4821
```

### Kết luận

```text
a/ 0.5600
b/ 0.4821
```

---

## Bài 1.8. Chuyển bi giữa hai hộp

### Đề bài

Hộp A có **5 bi đỏ**, **3 bi xanh**. Hộp B có **4 bi đỏ**, **6 bi xanh**. Rút ngẫu nhiên 1 viên bi từ hộp A chuyển sang hộp B, sau đó rút ngẫu nhiên 1 viên bi từ hộp B.

Yêu cầu:

a. Tính xác suất rút ở hộp B được bi đỏ.  
b. Biết rút ở hộp B được bi đỏ, tính xác suất viên bi chuyển từ hộp A sang hộp B là bi xanh.

### Nhận diện dạng

Hộp B thay đổi tùy màu bi chuyển từ A. Phải tách trường hợp theo viên chuyển.

### Bảng trường hợp

| Trường hợp | Xác suất chuyển từ A | Hộp B sau khi chuyển | Xác suất rút đỏ từ B | Tích |
|---:|---:|---|---:|---:|
| 1. Chuyển đỏ | `5/8` | 5 đỏ, 6 xanh | `5/11` | `5/8×5/11` |
| 2. Chuyển xanh | `3/8` | 4 đỏ, 7 xanh | `4/11` | `3/8×4/11` |

### Giải từng bước

#### a. Xác suất rút đỏ ở B

```math
P(Đ_B)=\frac58\times\frac5{11}+\frac38\times\frac4{11}=0.4205
```

#### b. Biết rút đỏ ở B, xác suất viên chuyển là xanh

Nhánh cần xét là “chuyển xanh rồi rút đỏ”:

```math
P(\text{chuyển xanh và rút đỏ})=\frac38\times\frac4{11}
```

Tổng xác suất rút đỏ là `0.4205`.

```math
P(\text{chuyển xanh}|Đ_B)=\frac{\frac38\times\frac4{11}}{0.4205}=0.3243
```

### Kết luận

```text
a/ 0.4205
b/ 0.3243
```

---

## Bài 1.9. Tỷ lệ mắc bệnh theo giới tính

### Đề bài

Một vùng dân cư có **55% nữ** và **45% nam**. Tỷ lệ mắc bệnh M ở nữ là **20%**, ở nam là **10%**.

Chọn ngẫu nhiên 1 người trong vùng.

Yêu cầu:

a. Tính xác suất người đó mắc bệnh M.  
b. Biết người đó mắc bệnh M, tính xác suất người đó là nam.

### Giải từng bước

Gọi `M` là biến cố mắc bệnh.

#### a. Xác suất mắc bệnh

| Nhánh | Xác suất nhóm | Xác suất mắc bệnh | Tích |
|---|---:|---:|---:|
| Nữ → bệnh | 0.55 | 0.20 | 0.110 |
| Nam → bệnh | 0.45 | 0.10 | 0.045 |

```math
P(M)=0.110+0.045=0.1550
```

#### b. Biết mắc bệnh, xác suất là nam

```math
P(\text{nam}|M)=\frac{0.45\times0.10}{0.155}=0.2903
```

### Kết luận

```text
a/ 0.1550
b/ 0.2903
```

---

## Bài 1.10. Tung xu rồi rút bi

### Đề bài

Tung một đồng xu cân đối. Nếu đồng xu ra **sấp**, bỏ vào bình 1 bi đỏ và 2 bi vàng. Nếu đồng xu ra **ngửa**, bỏ vào bình 2 bi đỏ và 2 bi vàng. Sau đó rút ngẫu nhiên 1 viên bi từ bình.

Yêu cầu:

a. Tính xác suất rút được bi đỏ.  
b. Biết rút được bi đỏ, tính xác suất đồng xu đã ra ngửa.

### Bảng nhánh

| Nhánh | Xác suất tung xu | Bình sau khi bỏ bi | Xác suất rút đỏ | Tích |
|---|---:|---|---:|---:|
| Sấp → đỏ | `1/2` | 1 đỏ, 2 vàng | `1/3` | `1/6` |
| Ngửa → đỏ | `1/2` | 2 đỏ, 2 vàng | `2/4` | `1/4` |

### Giải từng bước

#### a. Xác suất rút đỏ

```math
P(Đ)=\frac12\times\frac13+\frac12\times\frac24
```

```math
P(Đ)=\frac16+\frac14=0.4167
```

#### b. Biết rút đỏ, xác suất đồng xu ra ngửa

```math
P(\text{ngửa}|Đ)=\frac{\frac12\times\frac24}{0.4167}=0.6000
```

### Kết luận

```text
a/ 0.4167
b/ 0.6000
```

---

# MỤC 2. PHÂN PHỐI CHUẨN

## Khung tư duy Mục 2

Khi đề ghi:

```math
X\sim N(\mu,\sigma^2)
```

thì:

```text
μ là trung bình
σ² là phương sai
σ = căn bậc hai của phương sai
```

Đổi về chuẩn tắc:

```math
Z=\frac{X-\mu}{\sigma}\sim N(0,1)
```

Công thức xác suất khoảng:

```math
P(a<X<b)=\Phi\left(\frac{b-\mu}{\sigma}\right)-\Phi\left(\frac{a-\mu}{\sigma}\right)
```

Nếu tìm `T`:

```math
P(X<T)=p\Rightarrow T=\mu+\sigma z_p
```

Nếu đề cho `P(X>T)=p`, đổi thành:

```math
P(X<T)=1-p
```

## Bảng tra dùng trong Mục 2

| `z` | `Φ(z)` |
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

## Bài 2.1

### Đề bài

`X~N(60,64)`.  
a. Tính `P(50<X<70)`.  
b. Tìm `T` sao cho `P(X<T)=0.90`.

### Giải từng bước

Ta có:

```math
\mu=60,\quad \sigma=\sqrt{64}=8
```

#### a. Tính xác suất

```math
z_1=\frac{50-60}{8}=-1.25
```

```math
z_2=\frac{70-60}{8}=1.25
```

```math
P(50<X<70)=P(-1.25<Z<1.25)
```

Từ bảng:

```math
\Phi(-1.25)=0.1056,\quad \Phi(1.25)=0.8944
```

```math
P=0.8944-0.1056=0.7888\approx0.7887
```

#### b. Tìm T

```math
P(X<T)=0.90\Rightarrow z_{0.90}=1.2816
```

```math
T=60+8\times1.2816=70.2528\approx70.2524
```

### Kết luận

```text
a/ 0.7887
b/ T≈70.2524
```

---

## Bài 2.2

### Đề bài

`X~N(100,225)`.  
a. Tính `P(85<X<120)`.  
b. Tìm `T` sao cho `P(X<T)=0.95`.

### Giải từng bước

```math
\mu=100,\quad \sigma=\sqrt{225}=15
```

```math
z_1=\frac{85-100}{15}=-1
```

```math
z_2=\frac{120-100}{15}=1.3333
```

```math
P=\Phi(1.3333)-\Phi(-1)=0.9088-0.1587=0.7501
```

```math
z_{0.95}=1.6449
```

```math
T=100+15\times1.6449=124.6728
```

### Kết luận

```text
a/ 0.7501
b/ T≈124.6728
```

---

## Bài 2.3

### Đề bài

`X~N(500,1600)`.  
a. Tính `P(450<X<560)`.  
b. Tìm `T` sao cho `P(X<T)=0.10`.

### Giải từng bước

```math
\mu=500,\quad \sigma=\sqrt{1600}=40
```

```math
z_1=\frac{450-500}{40}=-1.25
```

```math
z_2=\frac{560-500}{40}=1.5
```

```math
P=\Phi(1.5)-\Phi(-1.25)=0.9332-0.1056=0.8276\approx0.8275
```

```math
z_{0.10}=-1.2816
```

```math
T=500+40\times(-1.2816)=448.736\approx448.7379
```

### Kết luận

```text
a/ 0.8275
b/ T≈448.7379
```

---

## Bài 2.4

### Đề bài

`X~N(170,36)`.  
a. Tính `P(160<X<180)`.  
b. Tìm `T` sao cho `P(X>T)=0.80`.

### Giải từng bước

```math
\mu=170,\quad \sigma=6
```

```math
z_1=\frac{160-170}{6}=-1.6667
```

```math
z_2=\frac{180-170}{6}=1.6667
```

```math
P=\Phi(1.6667)-\Phi(-1.6667)=0.9522-0.0478=0.9044
```

Câu b là xác suất bên phải:

```math
P(X>T)=0.80\Rightarrow P(X<T)=0.20
```

```math
z_{0.20}=-0.8416
```

```math
T=170+6\times(-0.8416)=164.9504\approx164.9503
```

### Kết luận

```text
a/ 0.9044
b/ T≈164.9503
```

---

## Bài 2.5

### Đề bài

`X~N(30,16)`.  
a. Tính `P(25<X<35)`.  
b. Tìm `T` sao cho `P(X>T)=0.05`.

### Giải từng bước

```math
\mu=30,\quad \sigma=4
```

```math
z_1=-1.25,\quad z_2=1.25
```

```math
P=0.8944-0.1056=0.7888\approx0.7887
```

```math
P(X>T)=0.05\Rightarrow P(X<T)=0.95
```

```math
z_{0.95}=1.6449
```

```math
T=30+4\times1.6449=36.5796\approx36.5794
```

### Kết luận

```text
a/ 0.7887
b/ T≈36.5794
```

---

## Bài 2.6

### Đề bài

`X~N(75,100)`.  
a. Tính `P(65<X<90)`.  
b. Tìm `T` sao cho `P(X<T)=0.975`.

### Giải từng bước

```math
\mu=75,\quad \sigma=10
```

```math
z_1=\frac{65-75}{10}=-1,\quad z_2=\frac{90-75}{10}=1.5
```

```math
P=\Phi(1.5)-\Phi(-1)=0.9332-0.1587=0.7745
```

```math
z_{0.975}=1.96
```

```math
T=75+10\times1.96=94.6000
```

### Kết luận

```text
a/ 0.7745
b/ T=94.6000
```

---

## Bài 2.7

### Đề bài

`X~N(12,6.25)`.  
a. Tính `P(9<X<15)`.  
b. Tìm `T` sao cho `P(X<T)=0.20`.

### Giải từng bước

```math
\mu=12,\quad \sigma=2.5
```

```math
z_1=-1.2,\quad z_2=1.2
```

```math
P=\Phi(1.2)-\Phi(-1.2)=0.8849-0.1151=0.7698\approx0.7699
```

```math
z_{0.20}=-0.8416
```

```math
T=12+2.5\times(-0.8416)=9.8960
```

### Kết luận

```text
a/ 0.7699
b/ T≈9.8960
```

---

## Bài 2.8

### Đề bài

`X~N(200,625)`.  
a. Tính `P(180<X<230)`.  
b. Tìm `T` sao cho `P(X>T)=0.85`.

### Giải từng bước

```math
\mu=200,\quad \sigma=25
```

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
T=200+25\times(-1.0364)=174.0900\approx174.0908
```

### Kết luận

```text
a/ 0.6731
b/ T≈174.0908
```

---

## Bài 2.9

### Đề bài

`X~N(3.5,0.16)`.  
a. Tính `P(3.0<X<4.1)`.  
b. Tìm `T` sao cho `P(X<T)=0.99`.

### Giải từng bước

```math
\mu=3.5,\quad \sigma=0.4
```

```math
z_1=-1.25,\quad z_2=1.5
```

```math
P=0.9332-0.1056=0.8276\approx0.8275
```

```math
z_{0.99}=2.3263
```

```math
T=3.5+0.4\times2.3263=4.4305
```

### Kết luận

```text
a/ 0.8275
b/ T≈4.4305
```

---

## Bài 2.10

### Đề bài

`X~N(1000,14400)`.  
a. Tính `P(850<X<1100)`.  
b. Tìm `T` sao cho `P(X>T)=0.15`.

### Giải từng bước

```math
\mu=1000,\quad \sigma=120
```

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
T=1000+120\times1.0364=1124.368\approx1124.3700
```

### Kết luận

```text
a/ 0.6920
b/ T≈1124.3700
```

---

# MỤC 3. BIẾN NGẪU NHIÊN LIÊN TỤC 1 BIẾN

## Khung tư duy Mục 3

Với hàm mật độ `f(x)`:

```text
Xác suất không phải là f(x), mà là diện tích dưới đồ thị f(x).
```

Thứ tự làm bắt buộc:

```text
Bước 1: Tìm k từ điều kiện ∫f(x)dx=1
Bước 2: Tính E(X)=∫xf(x)dx
Bước 3: Tính E(X²)=∫x²f(x)dx
Bước 4: Tính Var(X)=E(X²)-[E(X)]²
Bước 5: Tính xác suất bằng tích phân theo cận đề bài
```

---

## Bài 3.1

### Đề bài

```math
f(x)=kx,\quad 0<x<2
```

Tìm `k`, `E(X)`, `Var(X)`, `P(0.5<X<1.5)`.

### Giải từng bước

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

### Đáp số

```text
k=0.5, E(X)=1.3333, Var(X)=0.2222, P=0.5000
```

---

## Bài 3.2

### Đề bài

```math
f(x)=kx^2,\quad 0<x<3
```

Tìm `k`, `E(X)`, `Var(X)`, `P(1<X<2)`.

### Giải từng bước

```math
\int_0^3kx^2dx=1
```

```math
k\left[\frac{x^3}{3}\right]_0^3=1\Rightarrow 9k=1\Rightarrow k=\frac19
```

```math
E(X)=\int_0^3x\cdot\frac19x^2dx=\frac19\int_0^3x^3dx=2.2500
```

```math
E(X^2)=\int_0^3x^2\cdot\frac19x^2dx=\frac19\int_0^3x^4dx=5.4000
```

```math
Var(X)=5.4000-2.2500^2=0.3375
```

```math
P(1<X<2)=\int_1^2\frac19x^2dx=0.2593
```

### Đáp số

```text
k=0.1111, E=2.2500, Var=0.3375, P=0.2593
```

---

## Bài 3.3

### Đề bài

```math
f(x)=k(x+1),\quad 0<x<2
```

Tìm `k`, `E(X)`, `Var(X)`, `P(0.5<X<1.5)`.

### Giải từng bước

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

### Đáp số

```text
k=0.25, E=1.1667, Var=0.3056, P=0.5000
```

---

## Bài 3.4

### Đề bài

```math
f(x)=k(4-x),\quad 0<x<4
```

Tìm `k`, `E(X)`, `Var(X)`, `P(1<X<3)`.

### Giải từng bước

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

### Đáp số

```text
k=0.125, E=1.3333, Var=0.8889, P=0.5000
```

---

## Bài 3.5

### Đề bài

```math
f(x)=\frac{k}{x^2},\quad 1<x<3
```

Tìm `k`, `E(X)`, `Var(X)`, `P(1.5<X<2.5)`.

### Giải từng bước

```math
\int_1^3\frac{k}{x^2}dx=1
```

```math
k\left[-\frac1x\right]_1^3=1\Rightarrow k\left(1-\frac13\right)=1\Rightarrow k=1.5
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

### Đáp số

```text
k=1.5, E=1.6479, Var=0.2827, P=0.4000
```

---

## Bài 3.6

### Đề bài

```math
f(x)=k\sin x,\quad 0<x<\pi
```

Tìm `k`, `E(X)`, `Var(X)`, `P(\pi/6<X<\pi/2)`.

### Giải từng bước

```math
\int_0^\pi k\sin xdx=1
```

```math
k[-\cos x]_0^\pi=1\Rightarrow 2k=1\Rightarrow k=0.5
```

```math
E(X)=\int_0^\pi x\cdot0.5\sin xdx=1.5708
```

Hàm đối xứng quanh `π/2`, nên kỳ vọng bằng `π/2`.

```math
E(X^2)=\int_0^\pi x^2\cdot0.5\sin xdx=2.9348
```

```math
Var(X)=2.9348-1.5708^2=0.4674
```

```math
P(\pi/6<X<\pi/2)=\int_{\pi/6}^{\pi/2}0.5\sin xdx=0.4330
```

### Đáp số

```text
k=0.5, E=1.5708, Var=0.4674, P=0.4330
```

---

## Bài 3.7

### Đề bài

```math
f(x)=k(1-x^2),\quad -1<x<1
```

Tìm `k`, `E(X)`, `Var(X)`, `P(-0.5<X<0.5)`.

### Giải từng bước

```math
\int_{-1}^{1}k(1-x^2)dx=1
```

```math
k\left[x-\frac{x^3}{3}\right]_{-1}^{1}=1\Rightarrow k\cdot\frac43=1\Rightarrow k=0.75
```

Do miền và hàm mật độ đối xứng quanh 0:

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

### Đáp số

```text
k=0.75, E=0, Var=0.2, P=0.6875
```

---

## Bài 3.8

### Đề bài

```math
f(x)=k(2x+1),\quad 0<x<1
```

Tìm `k`, `E(X)`, `Var(X)`, `P(0.25<X<0.75)`.

### Giải từng bước

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

### Đáp số

```text
k=0.5, E=0.5833, Var=0.0764, P=0.5000
```

---

## Bài 3.9

### Đề bài

```math
f(x)=ke^{-x/2},\quad x>0
```

Tìm `k`, `E(X)`, `Var(X)`, `P(1<X<4)`.

### Giải từng bước

```math
\int_0^{+\infty}ke^{-x/2}dx=1
```

```math
\int_0^{+\infty}e^{-x/2}dx=2
```

```math
2k=1\Rightarrow k=0.5
```

Đây là phân phối mũ với `λ=0.5`, nên:

```math
E(X)=\frac1λ=2,\quad Var(X)=\frac1{λ^2}=4
```

```math
P(1<X<4)=\int_1^40.5e^{-x/2}dx=e^{-1/2}-e^{-2}=0.4712
```

### Đáp số

```text
k=0.5, E=2, Var=4, P=0.4712
```

---

## Bài 3.10

### Đề bài

```math
f(x)=kxe^{-x},\quad x>0
```

Tìm `k`, `E(X)`, `Var(X)`, `P(1<X<3)`.

### Giải từng bước

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

### Đáp số

```text
k=1, E=2, Var=2, P=0.5768
```

---

# MỤC 4. ƯỚC LƯỢNG VÀ KIỂM ĐỊNH

## Khung tư duy Mục 4

### 1. Nhận diện kỳ vọng hay tỷ lệ

```text
Có x̄, s, n  → bài về kỳ vọng μ
Có x trường hợp đạt / n mẫu → bài về tỷ lệ p
```

### 2. Khoảng tin cậy kỳ vọng

```math
\bar x\pm z\frac{s}{\sqrt n}
```

### 3. Khoảng tin cậy tỷ lệ

```math
\hat p\pm z\sqrt{\frac{\hat p(1-\hat p)}{n}}
```

### 4. Kiểm định

Làm theo thứ tự:

```text
Bước 1: Viết H0, H1
Bước 2: Tính Z
Bước 3: So với ngưỡng
Bước 4: Kết luận theo ngữ cảnh đề
```

---

## Bài 4.1. Trung bình chiều cao

### Đề bài

`n=64`, `x̄=168.5`, `s=7.2`.  
a. Ước lượng điểm cho kỳ vọng.  
b. Khoảng tin cậy 95%.  
c. Với `d=1.5`, tìm cỡ mẫu tối thiểu.  
d. Kiểm định `H0: μ=170`, `H1: μ<170`, mức ý nghĩa 5%.

### Giải từng bước

Ước lượng điểm:

```math
\hat\mu=\bar x=168.5
```

Khoảng tin cậy 95%, `z=1.96`:

```math
E=1.96\frac{7.2}{\sqrt{64}}=1.764
```

```math
CI=[168.5-1.764;168.5+1.764]=[166.736;170.264]
```

Cỡ mẫu:

```math
n\ge\left(\frac{1.96\times7.2}{1.5}\right)^2=88.47\Rightarrow n=89
```

Kiểm định:

```math
Z=\frac{168.5-170}{7.2/\sqrt{64}}=-1.6667
```

Kiểm định trái, bác bỏ nếu `Z<-1.645`. Vì `-1.6667<-1.645`, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận chiều cao trung bình nhỏ hơn 170.

---

## Bài 4.2. Thời gian xử lý

### Đề bài

`n=36`, `x̄=12.4`, `s=2.1`.  
a. Ước lượng điểm.  
b. Khoảng tin cậy 99%.  
c. Với `d=0.8`, tìm cỡ mẫu.  
d. Kiểm định `H0: μ=13`, `H1: μ≠13`, mức 5%.

### Giải từng bước

```math
\hat\mu=12.4
```

Với 99%, `z=2.576`:

```math
E=2.576\frac{2.1}{\sqrt{36}}=0.9016
```

```math
CI=[11.4984;13.3016]
```

```math
n\ge\left(\frac{2.576\times2.1}{0.8}\right)^2=45.69\Rightarrow n=46
```

```math
Z=\frac{12.4-13}{2.1/\sqrt{36}}=-1.7143
```

Hai phía, bác bỏ nếu `|Z|>1.96`. Vì `1.7143<1.96`, không bác bỏ `H0`.

### Kết luận

Chưa đủ cơ sở để kết luận trung bình khác 13.

---

## Bài 4.3. Điểm thi

### Đề bài

`n=100`, `x̄=7.1`, `s=1.3`.  
Khoảng tin cậy 90%, `d=0.25`, kiểm định `H0: μ=7.0`, `H1: μ>7.0`.

### Giải từng bước

```math
\hat\mu=7.1
```

```math
E=1.645\frac{1.3}{\sqrt{100}}=0.2139
```

```math
CI=[6.8861;7.3139]
```

```math
n\ge\left(\frac{1.645\times1.3}{0.25}\right)^2=73.18\Rightarrow n=74
```

```math
Z=\frac{7.1-7.0}{1.3/\sqrt{100}}=0.7692
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Không bác bỏ `H0`.

### Kết luận

Chưa đủ cơ sở để kết luận điểm trung bình lớn hơn 7.0.

---

## Bài 4.4. Khối lượng sản phẩm

### Đề bài

`n=49`, `x̄=50.8`, `s=4.5`.  
Khoảng tin cậy 95%, `d=1.0`, kiểm định `H0: μ=52`, `H1: μ<52`.

### Giải từng bước

```math
\hat\mu=50.8
```

```math
E=1.96\frac{4.5}{\sqrt{49}}=1.26
```

```math
CI=[49.5400;52.0600]
```

```math
n\ge\left(\frac{1.96\times4.5}{1.0}\right)^2=77.79\Rightarrow n=78
```

```math
Z=\frac{50.8-52}{4.5/\sqrt{49}}=-1.8667
```

Kiểm định trái, `-1.8667<-1.645`, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận khối lượng trung bình nhỏ hơn 52.

---

## Bài 4.5. Tuổi thọ pin

### Đề bài

`n=81`, `x̄=9.6`, `s=1.8`.  
Khoảng tin cậy 98%, `d=0.5`, kiểm định `H0: μ=9.2`, `H1: μ>9.2`.

### Giải từng bước

```math
\hat\mu=9.6
```

```math
E=2.326\frac{1.8}{\sqrt{81}}=0.4652
```

```math
CI=[9.1348;10.0652]
```

```math
n\ge\left(\frac{2.326\times1.8}{0.5}\right)^2=70.13\Rightarrow n=71
```

```math
Z=\frac{9.6-9.2}{1.8/\sqrt{81}}=2.0000
```

Kiểm định phải, `2.0000>1.645`, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận tuổi thọ pin trung bình lớn hơn 9.2.

---

## Bài 4.6. Tỷ lệ sản phẩm loại A

### Đề bài

Khảo sát `n=400`, có `x=52` sản phẩm mang đặc tính A.  
Khoảng tin cậy 95%, `d=0.03`, kiểm định `H0:p=0.1`, `H1:p>0.1`.

### Giải từng bước

```math
\hat p=\frac{52}{400}=0.1300
```

```math
E=1.96\sqrt{\frac{0.13(1-0.13)}{400}}=0.0330
```

```math
CI=[0.0970;0.1630]
```

```math
n\ge\frac{1.96^2\times0.13\times0.87}{0.03^2}=482.84\Rightarrow n=483
```

```math
Z=\frac{0.13-0.1}{\sqrt{0.1(1-0.1)/400}}=2.0000
```

Kiểm định phải, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận tỷ lệ lớn hơn 0.1.

---

## Bài 4.7. Tỷ lệ lỗi khảo sát 625 mẫu

### Đề bài

`n=625`, `x=75`. Khoảng tin cậy 99%, `d=0.025`, kiểm định `H0:p=0.15`, `H1:p<0.15`.

### Giải từng bước

```math
\hat p=\frac{75}{625}=0.1200
```

```math
E=2.576\sqrt{\frac{0.12\times0.88}{625}}=0.0335
```

```math
CI=[0.0865;0.1535]
```

```math
n\ge\frac{2.576^2\times0.12\times0.88}{0.025^2}=1120.82\Rightarrow n=1121
```

```math
Z=\frac{0.12-0.15}{\sqrt{0.15\times0.85/625}}=-2.1004
```

Kiểm định trái, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận tỷ lệ nhỏ hơn 0.15.

---

## Bài 4.8. Khảo sát 300 mẫu

### Đề bài

`n=300`, `x=138`. Khoảng tin cậy 90%, `d=0.05`, kiểm định `H0:p=0.5`, `H1:p≠0.5`.

### Giải từng bước

```math
\hat p=\frac{138}{300}=0.4600
```

```math
E=1.645\sqrt{\frac{0.46\times0.54}{300}}=0.0473
```

```math
CI=[0.4127;0.5073]
```

```math
n\ge\frac{1.645^2\times0.46\times0.54}{0.05^2}=268.89\Rightarrow n=269
```

```math
Z=\frac{0.46-0.5}{\sqrt{0.5\times0.5/300}}=-1.3856
```

Hai phía, không bác bỏ `H0`.

### Kết luận

Chưa đủ cơ sở để kết luận tỷ lệ khác 0.5.

---

## Bài 4.9. Khảo sát 1000 mẫu

### Đề bài

`n=1000`, `x=240`. Khoảng tin cậy 95%, `d=0.02`, kiểm định `H0:p=0.2`, `H1:p>0.2`.

### Giải từng bước

```math
\hat p=0.2400
```

```math
E=1.96\sqrt{\frac{0.24\times0.76}{1000}}=0.0265
```

```math
CI=[0.2135;0.2665]
```

```math
n\ge\frac{1.96^2\times0.24\times0.76}{0.02^2}=1751.77\Rightarrow n=1752
```

```math
Z=\frac{0.24-0.2}{\sqrt{0.2\times0.8/1000}}=3.1623
```

Kiểm định phải, bác bỏ `H0`.

### Kết luận

Có đủ cơ sở để kết luận tỷ lệ lớn hơn 0.2.

---

## Bài 4.10. Khảo sát 250 mẫu

### Đề bài

`n=250`, `x=30`. Khoảng tin cậy 98%, `d=0.04`, kiểm định `H0:p=0.1`, `H1:p≠0.1`.

### Giải từng bước

```math
\hat p=\frac{30}{250}=0.1200
```

```math
E=2.326\sqrt{\frac{0.12\times0.88}{250}}=0.0478
```

```math
CI=[0.0722;0.1678]
```

```math
n\ge\frac{2.326^2\times0.12\times0.88}{0.04^2}=357.11\Rightarrow n=358
```

```math
Z=\frac{0.12-0.1}{\sqrt{0.1\times0.9/250}}=1.0541
```

Hai phía, không bác bỏ `H0`.

### Kết luận

Chưa đủ cơ sở để kết luận tỷ lệ khác 0.1.

---

# MỤC 5. TƯƠNG QUAN VÀ HỒI QUY

## Khung tư duy Mục 5

Mỗi bài hồi quy làm 3 việc:

```text
1. Tính hệ số tương quan r
2. Nhận xét thuận/nghịch, mạnh/yếu
3. Lập phương trình hồi quy Ŷ=a+bX và dự đoán
```

Ý nghĩa:

```text
r > 0: X tăng thì Y có xu hướng tăng
r < 0: X tăng thì Y có xu hướng giảm
|r| gần 1: tương quan tuyến tính mạnh
```

Phương trình:

```math
\hat Y=a+bX
```

`b` cho biết X tăng 1 đơn vị thì Y dự đoán thay đổi trung bình bao nhiêu.

---

## Bài 5.1. Quảng cáo và doanh thu

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

### Giải từng bước

Kết quả tính bằng STAT:

```math
r=0.9982
```

Vì `r>0` và gần 1 nên tương quan thuận rất mạnh.

```math
\hat Y=8.8571+5.6429X
```

Dự đoán:

```math
\hat Y(7)=8.8571+5.6429\times7=48.3571
```

### Kết luận

`Y(7)=48.3571`.

---

## Bài 5.2. Giờ học và điểm thi

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

### Giải từng bước

```math
r=0.9983
```

Tương quan thuận rất mạnh.

```math
\hat Y=3.5714+0.6929X
```

```math
\hat Y(8)=3.5714+0.6929\times8=9.1143
```

### Kết luận

`Y(8)=9.1143`.

---

## Bài 5.3. Nhiệt độ và điện tiêu thụ

### Giải từng bước

```math
r=0.9894
```

```math
\hat Y=-2.8571+5.9143X
```

```math
\hat Y(27)=-2.8571+5.9143\times27=156.8286
```

### Kết luận

Tương quan thuận rất mạnh, `Y(27)=156.8286`.

---

## Bài 5.4. Tuổi máy và chi phí bảo trì

### Giải từng bước

```math
r=0.9912
```

```math
\hat Y=1.8667+2.8857X
```

```math
\hat Y(7)=22.0667
```

### Kết luận

Tương quan thuận rất mạnh.

---

## Bài 5.5. Giá bán và số lượng bán

### Giải từng bước

```math
r=-0.9920
```

`r` âm nên tương quan nghịch rất mạnh.

```math
\hat Y=147.3333-4.7000X
```

```math
\hat Y(15)=76.8333
```

### Kết luận

Giá tăng thì số lượng bán giảm.

---

## Bài 5.6. Nhân viên và sản lượng

### Giải từng bước

```math
r=0.9991
```

```math
\hat Y=4.5513+6.6923X
```

```math
\hat Y(11)=78.1667
```

### Kết luận

Tương quan thuận rất mạnh.

---

## Bài 5.7. Độ ẩm và tỷ lệ lỗi

### Giải từng bước

```math
r=0.9892
```

```math
\hat Y=-3.0629+0.1646X
```

```math
\hat Y(48)=4.8371
```

### Kết luận

Độ ẩm tăng thì tỷ lệ lỗi có xu hướng tăng.

---

## Bài 5.8. Tháng tuổi và khối lượng

### Giải từng bước

```math
r=0.9994
```

```math
\hat Y=3.6667+4.5333X
```

```math
\hat Y(7)=35.4000
```

### Kết luận

Tương quan thuận rất mạnh.

---

## Bài 5.9. Độ dài chương trình và số lỗi

### Giải từng bước

```math
r=0.9949
```

```math
\hat Y=-1.0667+1.6464X
```

```math
\hat Y(10)=15.3970
```

### Kết luận

Chương trình dài hơn thì số lỗi có xu hướng tăng.

---

## Bài 5.10. Kinh nghiệm và lương

### Giải từng bước

```math
r=0.9977
```

```math
\hat Y=6.1872+2.3498X
```

```math
\hat Y(7)=22.6355
```

### Kết luận

Kinh nghiệm tăng thì lương dự đoán tăng.

---

# CHECKLIST HỌC NHANH TRƯỚC KHI THI

## Xác suất nhiều nguồn

```text
Vẽ cây → nhân theo nhánh → cộng nhánh tạo ra kết quả → nếu hỏi ngược thì Bayes
```

## Tổ hợp

```text
Rút cùng lúc/chọn không thứ tự → C(n,k)
Đúng k → chọn đúng k nhóm cần + phần còn lại nhóm khác
Ít nhất → liệt kê hoặc dùng biến cố đối
```

## Phân phối chuẩn

```text
Đọc N(μ,σ²) → lấy σ
Chuẩn hóa Z=(X-μ)/σ
Khoảng → Φ(z2)-Φ(z1)
Tìm T → T=μ+σz
P(X>T) → đổi thành P(X<T)=1-p
```

## Mật độ liên tục

```text
Tìm k trước
Rồi mới E(X), E(X²), Var(X), xác suất
```

## Ước lượng - kiểm định

```text
x̄,s,n → kỳ vọng
x/n → tỷ lệ
Khoảng tin cậy = ước lượng ± sai số
Kiểm định = tính Z rồi so ngưỡng
```

## Hồi quy

```text
Tính r → nhận xét → lập Ŷ=a+bX → thay X dự đoán
```
