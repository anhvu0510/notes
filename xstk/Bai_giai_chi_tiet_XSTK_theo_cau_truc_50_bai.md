# BÀI GIẢI CHI TIẾT XÁC SUẤT - THỐNG KÊ

> File này mapping 1-1 với `Bai_tap_XSTK_theo_cau_truc_50_bai.md`.  
> Mục tiêu: người mất gốc đọc vào hiểu **vì sao chọn công thức**, **đề đang hỏi gì**, **từng bước biến đổi ra sao**, và **cách áp dụng lại trong phòng thi**.

---

## Cách đọc file này

Mỗi bài có 5 phần:

1. **Đề bài**: chép lại đúng bài trong file bài tập.
2. **Dữ kiện cần lấy**: lọc số liệu quan trọng.
3. **Nhận diện dạng**: giải thích vì sao dùng công thức đó.
4. **Giải từng bước**: thay số, tính toán, kết luận từng ý.
5. **Mẹo áp dụng**: gặp bài tương tự thì làm như thế nào.

---

# MỤC 1. XÁC SUẤT CHƯƠNG 1

## Khung tư duy chung

### Khi nào dùng xác suất đầy đủ?

Dùng khi một kết quả có thể xảy ra từ nhiều **nguồn/nhánh** khác nhau.

Ví dụ: sản phẩm lỗi có thể do dây chuyền A, B, C; rút bi đỏ có thể do chọn hộp I, II, III.

Công thức:

```math
P(A)=P(H_1)P(A|H_1)+P(H_2)P(A|H_2)+...+P(H_n)P(A|H_n)
```

Hiểu bằng lời: muốn A xảy ra, ta cộng toàn bộ đường đi có thể tạo ra A.

### Khi nào dùng Bayes?

Dùng khi đề cho biết kết quả đã xảy ra, rồi hỏi ngược lại nguyên nhân/nguồn.

Công thức:

```math
P(H_i|A)=\frac{P(H_i)P(A|H_i)}{P(A)}
```

Hiểu bằng lời:

- Mẫu số: tất cả các cách làm A xảy ra.
- Tử số: riêng nhánh vừa thuộc `H_i`, vừa làm A xảy ra.

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
P(Lỗi|A)=0.03, P(Lỗi|B)=0.05, P(Lỗi|C)=0.08
```

### Nhận diện dạng

Sản phẩm bị lỗi có thể đến từ A, B hoặc C. Đây là bài **nhiều nguồn tạo ra cùng một kết quả**, nên câu a dùng xác suất đầy đủ. Câu b đã biết sản phẩm bị lỗi, hỏi ngược lại có phải do C không, nên dùng Bayes.

### Cách suy nghĩ trước khi giải

Vẽ cây:

```text
A sản xuất 40% → lỗi 3%
B sản xuất 35% → lỗi 5%
C sản xuất 25% → lỗi 8%
```

Một sản phẩm lỗi có thể đi qua một trong ba nhánh trên. Vì ba nhánh không trùng nhau, ta cộng xác suất của ba nhánh.

### Giải chi tiết

Gọi `L` là biến cố “sản phẩm bị lỗi”.

#### a. Xác suất sản phẩm bị lỗi

Muốn sản phẩm lỗi, có 3 trường hợp:

1. Do A sản xuất và bị lỗi: xác suất `0.40 × 0.03`.
2. Do B sản xuất và bị lỗi: xác suất `0.35 × 0.05`.
3. Do C sản xuất và bị lỗi: xác suất `0.25 × 0.08`.

Vậy:

```math
P(L)=0.40\cdot0.03+0.35\cdot0.05+0.25\cdot0.08
```

```math
P(L)=0.012+0.0175+0.020=0.0495
```

#### b. Biết sản phẩm bị lỗi, xác suất do C sản xuất

Đề đã cho biết sản phẩm lỗi, tức ta chỉ xét trong nhóm sản phẩm lỗi. Trong nhóm đó, hỏi phần thuộc dây chuyền C là bao nhiêu.

Dùng Bayes:

```math
P(C|L)=\frac{P(C\cap L)}{P(L)}
```

Trong đó:

```math
P(C\cap L)=P(C)P(L|C)=0.25\cdot0.08=0.020
```

Do đó:

```math
P(C|L)=\frac{0.020}{0.0495}=0.4040
```

### Kết luận

- a. Xác suất sản phẩm bị lỗi là `0.0495`.
- b. Nếu biết sản phẩm bị lỗi, xác suất nó do dây chuyền C sản xuất là `0.4040`.

### Mẹo áp dụng

Gặp bài “nhiều phân xưởng/dây chuyền/nhóm tạo ra lỗi” thì luôn viết cây xác suất. Câu hỏi “biết đã lỗi” gần như chắc chắn là Bayes.

---

## Bài 1.2. Chọn hộp rồi rút bi

### Đề bài

Có 3 hộp I, II, III được chọn với xác suất lần lượt **0,30**, **0,50**, **0,20**. Tỷ lệ bi đỏ trong các hộp I, II, III lần lượt là **70%**, **40%**, **20%**.

Chọn ngẫu nhiên 1 hộp, sau đó rút ngẫu nhiên 1 viên bi.

Yêu cầu:

a. Tính xác suất rút được bi đỏ.  
b. Biết đã rút được bi đỏ, tính xác suất viên bi đó được rút từ hộp I.

### Dữ kiện cần lấy

```text
P(I)=0.30, P(II)=0.50, P(III)=0.20
P(Đỏ|I)=0.70, P(Đỏ|II)=0.40, P(Đỏ|III)=0.20
```

### Nhận diện dạng

Rút được bi đỏ phụ thuộc vào hộp được chọn. Vì vậy phải chia theo từng hộp. Câu a dùng xác suất đầy đủ, câu b dùng Bayes.

### Giải chi tiết

Gọi `Đ` là biến cố rút được bi đỏ.

#### a. Xác suất rút được bi đỏ

Có 3 nhánh tạo ra bi đỏ:

```text
Chọn hộp I rồi rút đỏ
Chọn hộp II rồi rút đỏ
Chọn hộp III rồi rút đỏ
```

```math
P(Đ)=P(I)P(Đ|I)+P(II)P(Đ|II)+P(III)P(Đ|III)
```

```math
P(Đ)=0.30\cdot0.70+0.50\cdot0.40+0.20\cdot0.20
```

```math
P(Đ)=0.21+0.20+0.04=0.4500
```

#### b. Biết rút được đỏ, xác suất từ hộp I

Ta chỉ xét trong nhóm các lần rút được đỏ. Trong đó, phần đến từ hộp I là:

```math
P(I|Đ)=\frac{P(I)P(Đ|I)}{P(Đ)}
```

```math
P(I|Đ)=\frac{0.30\cdot0.70}{0.45}=\frac{0.21}{0.45}=0.4667
```

### Kết luận

- a. `0.4500`.
- b. `0.4667`.

### Mẹo áp dụng

Bài chọn hộp rồi rút bi thường có 2 tầng: **chọn hộp → rút bi**. Cứ nhân theo nhánh, cộng các nhánh cùng kết quả.

---

## Bài 1.3. Xét nghiệm bệnh

### Đề bài

Một bệnh có tỷ lệ mắc trong cộng đồng là **1%**. Một loại xét nghiệm có xác suất cho kết quả dương tính nếu người đó thật sự mắc bệnh là **95%**. Nếu người đó không mắc bệnh, xác suất xét nghiệm vẫn cho dương tính giả là **4%**.

Yêu cầu:

a. Tính xác suất một người được chọn ngẫu nhiên có kết quả xét nghiệm dương tính.  
b. Biết kết quả xét nghiệm là dương tính, tính xác suất người đó thật sự mắc bệnh.

### Dữ kiện cần lấy

```text
P(Bệnh)=0.01
P(Không bệnh)=0.99
P(+|Bệnh)=0.95
P(+|Không bệnh)=0.04
```

### Nhận diện dạng

Dương tính có 2 nguyên nhân: bệnh thật hoặc dương tính giả. Câu a dùng xác suất đầy đủ. Câu b hỏi ngược từ “dương tính” về “có bệnh thật không”, nên dùng Bayes.

### Giải chi tiết

Gọi:

- `B`: mắc bệnh.
- `K`: không mắc bệnh.
- `+`: xét nghiệm dương tính.

#### a. Xác suất dương tính

Một người dương tính có thể thuộc 2 nhóm:

```text
Bị bệnh thật → test dương tính
Không bệnh → test dương tính giả
```

```math
P(+)=P(B)P(+|B)+P(K)P(+|K)
```

```math
P(+)=0.01\cdot0.95+0.99\cdot0.04
```

```math
P(+)=0.0095+0.0396=0.0491
```

#### b. Biết dương tính, xác suất thật sự mắc bệnh

Trong toàn bộ người dương tính, ta hỏi tỷ lệ người bệnh thật.

```math
P(B|+)=\frac{P(B)P(+|B)}{P(+)}
```

```math
P(B|+)=\frac{0.01\cdot0.95}{0.0491}=0.1935
```

### Vì sao kết quả chỉ khoảng 19.35%?

Do bệnh rất hiếm, chỉ 1%. Nhóm không bệnh là 99%, rất lớn. Dù dương tính giả chỉ 4%, nhưng 4% của nhóm rất lớn vẫn tạo ra nhiều người dương tính giả.

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

### Nhận diện dạng

Bắn độc lập nên khi cần xác suất cả hai cùng xảy ra thì nhân. Câu b là xác suất có điều kiện: đã biết đúng 1 viên trúng, hỏi viên đó là của A.

### Giải chi tiết

Gọi:

- `A`: A bắn trúng, `P(A)=0.75`.
- `B`: B bắn trúng, `P(B)=0.60`.
- A trật: `P(A^c)=0.25`.
- B trật: `P(B^c)=0.40`.

#### a. Cả hai cùng trúng

Vì độc lập:

```math
P(A\cap B)=P(A)P(B)=0.75\cdot0.60=0.4500
```

#### b. Biết đúng 1 viên trúng

Đúng 1 viên trúng gồm đúng 2 trường hợp:

```text
A trúng, B trật
A trật, B trúng
```

Xác suất đúng 1 viên trúng:

```math
P(\text{đúng 1})=P(A\cap B^c)+P(A^c\cap B)
```

```math
P(\text{đúng 1})=0.75\cdot0.40+0.25\cdot0.60=0.30+0.15=0.45
```

Trong biến cố “đúng 1 viên trúng”, viên trúng là của A khi xảy ra nhánh `A trúng, B trật`.

```math
P(A\text{ trúng}|\text{đúng 1})=\frac{0.75\cdot0.40}{0.45}=0.6667
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

### Dữ kiện cần lấy

```text
Bộ bài có 52 lá
Có 4 lá Ách
Có 48 lá không phải Ách
Rút 5 lá cùng lúc
```

### Nhận diện dạng

Rút cùng lúc nghĩa là thứ tự không quan trọng. Vì vậy dùng tổ hợp `C(n,k)`. Không dùng chỉnh hợp vì lá bài rút ra không xếp theo thứ tự.

### Giải chi tiết

Tổng số cách rút 5 lá bất kỳ:

```math
C_{52}^{5}
```

#### a. Có ít nhất 1 lá Ách

“Ít nhất 1” nghĩa là 1, 2, 3 hoặc 4 lá Ách. Nếu cộng từng trường hợp sẽ dài. Cách nhanh là dùng biến cố đối.

Biến cố đối của “ít nhất 1 Ách” là “không có lá Ách nào”.

Số cách không có Ách: chọn cả 5 lá từ 48 lá không Ách.

```math
P(\text{không Ách})=\frac{C_{48}^{5}}{C_{52}^{5}}
```

Do đó:

```math
P(\text{ít nhất 1 Ách})=1-\frac{C_{48}^{5}}{C_{52}^{5}}=0.3412
```

#### b. Có đúng 2 lá Ách

Muốn đúng 2 Ách thì 3 lá còn lại bắt buộc không phải Ách.

- Chọn 2 từ 4 lá Ách: `C_4^2`.
- Chọn 3 từ 48 lá không Ách: `C_48^3`.

```math
P=\frac{C_4^2C_{48}^{3}}{C_{52}^{5}}=0.0399
```

### Kết luận

- a. `0.3412`.
- b. `0.0399`.

### Mẹo áp dụng

Gặp “ít nhất 1” thì nghĩ ngay tới `1 - không có`. Gặp “đúng k” thì chọn đúng k phần tử loại cần, phần còn lại chọn từ nhóm không phải loại đó.

---

## Bài 1.6. Rút bi cùng lúc

### Đề bài

Một hộp có **8 bi xanh** và **12 bi đỏ**. Lấy ngẫu nhiên cùng lúc 4 viên bi.

Yêu cầu:

a. Tính xác suất lấy được đúng 2 bi xanh.  
b. Tính xác suất lấy được ít nhất 2 bi xanh.

### Nhận diện dạng

Lấy cùng lúc 4 bi nên không xét thứ tự. Dùng tổ hợp.

### Giải chi tiết

Tổng số bi:

```math
8+12=20
```

Tổng số cách lấy 4 bi:

```math
C_{20}^{4}
```

#### a. Đúng 2 bi xanh

Nếu lấy đúng 2 xanh thì còn lại là 2 đỏ.

```math
P=\frac{C_8^2C_{12}^2}{C_{20}^{4}}=0.3814
```

#### b. Ít nhất 2 bi xanh

Ít nhất 2 xanh gồm 3 trường hợp:

```text
2 xanh, 2 đỏ
3 xanh, 1 đỏ
4 xanh, 0 đỏ
```

Vậy:

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

### Nhận diện dạng

Sinh viên đậu có thể thuộc năm nhất, năm hai hoặc năm ba. Đây là xác suất đầy đủ. Câu b hỏi ngược trong nhóm đã đậu, nên dùng Bayes.

### Giải chi tiết

Gọi `D` là biến cố sinh viên đậu môn X.

Câu a:

```math
P(D)=0.25\cdot0.80+0.45\cdot0.60+0.30\cdot0.30
```

```math
P(D)=0.20+0.27+0.09=0.5600
```

Câu b:

Nhánh “năm hai và đậu” có xác suất:

```math
0.45\cdot0.60=0.27
```

Toàn bộ xác suất đậu là `0.56`. Vậy:

```math
P(\text{năm hai}|D)=\frac{0.27}{0.56}=0.4821
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

### Nhận diện dạng

Rút ở hộp B sau khi hộp B bị thay đổi. Hộp B thay đổi theo màu bi chuyển từ A. Vì vậy phải chia trường hợp theo màu bi chuyển.

### Giải chi tiết

Hộp A có tổng `8` bi.

#### Trường hợp 1: chuyển đỏ từ A sang B

```math
P(\text{chuyển đỏ})=\frac58
```

Khi đó hộp B từ `4 đỏ, 6 xanh` thành `5 đỏ, 6 xanh`, tổng 11 bi.

```math
P(\text{rút đỏ từ B}|\text{chuyển đỏ})=\frac5{11}
```

Xác suất nhánh này:

```math
\frac58\cdot\frac5{11}
```

#### Trường hợp 2: chuyển xanh từ A sang B

```math
P(\text{chuyển xanh})=\frac38
```

Khi đó hộp B thành `4 đỏ, 7 xanh`, tổng 11 bi.

```math
P(\text{rút đỏ từ B}|\text{chuyển xanh})=\frac4{11}
```

Xác suất nhánh này:

```math
\frac38\cdot\frac4{11}
```

#### a. Xác suất rút đỏ ở B

Cộng hai nhánh tạo ra đỏ:

```math
P(Đ_B)=\frac58\cdot\frac5{11}+\frac38\cdot\frac4{11}=0.4205
```

#### b. Biết rút đỏ ở B, xác suất đã chuyển xanh

Đây là Bayes. Tử số là nhánh “chuyển xanh rồi rút đỏ”. Mẫu số là toàn bộ xác suất rút đỏ ở B.

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

### Nhận diện dạng

Người mắc bệnh có thể thuộc nhóm nữ hoặc nhóm nam. Câu a dùng xác suất đầy đủ. Câu b hỏi ngược từ “mắc bệnh” về giới tính nam, nên dùng Bayes.

### Giải chi tiết

Gọi `M` là biến cố mắc bệnh.

Câu a:

```math
P(M)=P(\text{nữ})P(M|\text{nữ})+P(\text{nam})P(M|\text{nam})
```

```math
P(M)=0.55\cdot0.20+0.45\cdot0.10=0.11+0.045=0.1550
```

Câu b:

```math
P(\text{nam}|M)=\frac{P(\text{nam})P(M|\text{nam})}{P(M)}
```

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

### Nhận diện dạng

Kết quả trong bình phụ thuộc vào đồng xu. Đây là cây xác suất 2 tầng: tung xu rồi rút bi.

### Giải chi tiết

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
P(Đ)=\frac12\cdot\frac13+\frac12\cdot\frac24
```

```math
P(Đ)=\frac16+\frac14=0.4167
```

Câu b:

```math
P(\text{ngửa}|Đ)=\frac{P(\text{ngửa})P(Đ|\text{ngửa})}{P(Đ)}
```

```math
P(\text{ngửa}|Đ)=\frac{\frac12\cdot\frac24}{0.4167}=0.6000
```

### Kết luận

- a. `0.4167`.
- b. `0.6000`.

---

# MỤC 2. BIẾN NGẪU NHIÊN LIÊN TỤC PHÂN PHỐI CHUẨN

## Khung tư duy chung

Nếu `X ~ N(μ, σ²)`, ta không thể tra trực tiếp mọi bảng với `X`. Ta đổi về chuẩn tắc `Z ~ N(0,1)`:

```math
Z=\frac{X-\mu}{\sigma}
```

Với khoảng:

```math
P(a<X<b)=P\left(\frac{a-\mu}{\sigma}<Z<\frac{b-\mu}{\sigma}\right)
```

Với bài tìm `T`:

```math
T=\mu+\sigma z_p
```

trong đó `z_p` là giá trị sao cho `P(Z<z_p)=p`.

---

## Bài 2.1

### Đề bài

Cho biến ngẫu nhiên `X ~ N(60, 64)`.

Yêu cầu:

a. Tính `P(50 < X < 70)`.  
b. Tìm `T` sao cho `P(X < T) = 0,90`.

### Nhận diện dạng

Đây là bài phân phối chuẩn. Số thứ hai trong `N(60,64)` là phương sai, nên phải lấy căn để được độ lệch chuẩn.

### Giải chi tiết

```math
\mu=60,\quad \sigma=\sqrt{64}=8
```

#### a. Tính xác suất khoảng

Chuẩn hóa cận dưới:

```math
z_1=\frac{50-60}{8}=-1.25
```

Chuẩn hóa cận trên:

```math
z_2=\frac{70-60}{8}=1.25
```

Do đó:

```math
P(50<X<70)=P(-1.25<Z<1.25)
```

```math
P=\Phi(1.25)-\Phi(-1.25)=0.7887
```

#### b. Tìm T

`P(X<T)=0.90` nghĩa là T nằm tại mốc 90% bên trái. Tra bảng chuẩn:

```math
z_{0.90}=1.2816
```

Đổi lại về X:

```math
T=60+8\cdot1.2816=70.2524
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

### Giải chi tiết

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
P(85<X<120)=P(-1<Z<1.3333)=0.7501
```

Với `P(X<T)=0.95`:

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

### Giải chi tiết

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
P(450<X<560)=P(-1.25<Z<1.5)=0.8275
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

Cho biến ngẫu nhiên `X ~ N(170, 36)`.

Yêu cầu:

a. Tính `P(160 < X < 180)`.  
b. Tìm `T` sao cho `P(X > T) = 0,80`.

### Giải chi tiết

```math
\mu=170,\quad \sigma=\sqrt{36}=6
```

```math
z_1=\frac{160-170}{6}=-1.6667
```

```math
z_2=\frac{180-170}{6}=1.6667
```

```math
P(160<X<180)=P(-1.6667<Z<1.6667)=0.9044
```

Câu b cho xác suất bên phải. Bảng chuẩn/máy InvN thường dùng diện tích bên trái, nên đổi:

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

Cho biến ngẫu nhiên `X ~ N(30, 16)`.

Yêu cầu:

a. Tính `P(25 < X < 35)`.  
b. Tìm `T` sao cho `P(X > T) = 0,05`.

### Giải chi tiết

```math
\mu=30,\quad \sigma=\sqrt{16}=4
```

```math
z_1=\frac{25-30}{4}=-1.25,\quad z_2=\frac{35-30}{4}=1.25
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

Cho biến ngẫu nhiên `X ~ N(75, 100)`.

Yêu cầu:

a. Tính `P(65 < X < 90)`.  
b. Tìm `T` sao cho `P(X < T) = 0,975`.

### Giải chi tiết

```math
\mu=75,\quad \sigma=10
```

```math
z_1=\frac{65-75}{10}=-1
```

```math
z_2=\frac{90-75}{10}=1.5
```

```math
P(65<X<90)=P(-1<Z<1.5)=0.7745
```

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

### Giải chi tiết

```math
\mu=12,\quad \sigma=\sqrt{6.25}=2.5
```

```math
z_1=\frac{9-12}{2.5}=-1.2,\quad z_2=\frac{15-12}{2.5}=1.2
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

Cho biến ngẫu nhiên `X ~ N(200, 625)`.

Yêu cầu:

a. Tính `P(180 < X < 230)`.  
b. Tìm `T` sao cho `P(X > T) = 0,85`.

### Giải chi tiết

```math
\mu=200,\quad \sigma=\sqrt{625}=25
```

```math
z_1=\frac{180-200}{25}=-0.8,\quad z_2=\frac{230-200}{25}=1.2
```

```math
P(180<X<230)=P(-0.8<Z<1.2)=0.6731
```

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

### Giải chi tiết

```math
\mu=3.5,\quad \sigma=\sqrt{0.16}=0.4
```

```math
z_1=\frac{3.0-3.5}{0.4}=-1.25
```

```math
z_2=\frac{4.1-3.5}{0.4}=1.5
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

Cho biến ngẫu nhiên `X ~ N(1000, 14400)`.

Yêu cầu:

a. Tính `P(850 < X < 1100)`.  
b. Tìm `T` sao cho `P(X > T) = 0,15`.

### Giải chi tiết

```math
\mu=1000,\quad \sigma=\sqrt{14400}=120
```

```math
z_1=\frac{850-1000}{120}=-1.25
```

```math
z_2=\frac{1100-1000}{120}=0.8333
```

```math
P(850<X<1100)=P(-1.25<Z<0.8333)=0.6915
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

## Khung tư duy chung

Một hàm mật độ không phải là xác suất trực tiếp tại một điểm. Xác suất nằm trong **diện tích dưới đồ thị**.

Với `f(x)=kg(x)`:

1. Tìm `k` để tổng diện tích bằng 1:

```math
\int f(x)dx=1
```

2. Tính kỳ vọng:

```math
E(X)=\int xf(x)dx
```

3. Tính phương sai qua moment bậc hai:

```math
Var(X)=E(X^2)-[E(X)]^2
```

4. Tính xác suất khoảng:

```math
P(a<X<b)=\int_a^bf(x)dx
```

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

### Giải chi tiết

#### a. Tìm k

Vì `f(x)` là mật độ nên diện tích dưới đồ thị từ 0 đến 2 phải bằng 1:

```math
\int_0^2kx\,dx=1
```

Đưa `k` ra ngoài tích phân:

```math
k\int_0^2x\,dx=1
```

```math
k\left[\frac{x^2}{2}\right]_0^2=1
```

```math
k\cdot2=1\Rightarrow k=0.5
```

#### b. Tính E(X) và Var(X)

Kỳ vọng là trung bình lý thuyết:

```math
E(X)=\int_0^2xf(x)dx
```

Thay `f(x)=0.5x`:

```math
E(X)=\int_0^2x\cdot0.5x\,dx=0.5\int_0^2x^2dx
```

```math
E(X)=0.5\left[\frac{x^3}{3}\right]_0^2=\frac43=1.3333
```

Muốn tính phương sai cần `E(X²)` trước:

```math
E(X^2)=\int_0^2x^2f(x)dx=\int_0^2x^2\cdot0.5x\,dx
```

```math
E(X^2)=0.5\int_0^2x^3dx=0.5\left[\frac{x^4}{4}\right]_0^2=2
```

```math
Var(X)=E(X^2)-[E(X)]^2=2-\left(\frac43\right)^2=0.2222
```

#### c. Tính xác suất

```math
P(0.5<X<1.5)=\int_{0.5}^{1.5}0.5x\,dx
```

```math
=0.5\left[\frac{x^2}{2}\right]_{0.5}^{1.5}=0.5000
```

### Kết luận

`k=0.5`, `E(X)=1.3333`, `Var(X)=0.2222`, `P=0.5000`.

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

### Giải chi tiết

```math
\int_0^3kx^2dx=1
```

```math
k\left[\frac{x^3}{3}\right]_0^3=1\Rightarrow 9k=1\Rightarrow k=\frac19
```

Sau khi có `k`, mật độ là:

```math
f(x)=\frac19x^2
```

Kỳ vọng:

```math
E(X)=\int_0^3x\cdot\frac19x^2dx=\frac19\int_0^3x^3dx=2.2500
```

Moment bậc hai:

```math
E(X^2)=\int_0^3x^2\cdot\frac19x^2dx=\frac19\int_0^3x^4dx=5.4000
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

`k=0.1111`, `E(X)=2.2500`, `Var(X)=0.3375`, `P=0.2593`.

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

### Giải chi tiết

Tìm `k`:

```math
\int_0^2k(x+1)dx=1
```

```math
k\left[\frac{x^2}{2}+x\right]_0^2=1
```

```math
k(2+2)=1\Rightarrow 4k=1\Rightarrow k=0.25
```

Kỳ vọng:

```math
E(X)=\int_0^2x\cdot0.25(x+1)dx
```

```math
=0.25\int_0^2(x^2+x)dx=1.1667
```

Moment bậc hai:

```math
E(X^2)=\int_0^2x^2\cdot0.25(x+1)dx=1.6667
```

Phương sai:

```math
Var(X)=1.6667-1.1667^2=0.3056
```

Xác suất:

```math
P(0.5<X<1.5)=\int_{0.5}^{1.5}0.25(x+1)dx=0.5000
```

### Kết luận

`k=0.25`, `E(X)=1.1667`, `Var(X)=0.3056`, `P=0.5000`.

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

### Giải chi tiết

```math
\int_0^4k(4-x)dx=1
```

```math
k\left[4x-\frac{x^2}{2}\right]_0^4=1
```

```math
k(16-8)=1\Rightarrow 8k=1\Rightarrow k=0.125
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

`k=0.125`, `E(X)=1.3333`, `Var(X)=0.8889`, `P=0.5000`.

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

### Giải chi tiết

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
k\left(-\frac13+1\right)=1\Rightarrow k\cdot\frac23=1\Rightarrow k=1.5
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

### Kết luận

`k=1.5`, `E(X)=1.6479`, `Var(X)=0.2827`, `P=0.4000`.

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

### Giải chi tiết

```math
\int_0^\pi k\sin xdx=1
```

```math
k[-\cos x]_0^\pi=1
```

```math
k[-\cos\pi-(-\cos0)]=k[1-(-1)]=2k=1
```

```math
k=0.5
```

Kỳ vọng:

```math
E(X)=\int_0^\pi x\cdot0.5\sin xdx=1.5708
```

Có thể hiểu nhanh: hàm `sin x` trên `(0,π)` đối xứng quanh `π/2`, nên trung bình nằm tại `π/2`.

```math
E(X^2)=\int_0^\pi x^2\cdot0.5\sin xdx=2.9348
```

```math
Var(X)=2.9348-1.5708^2=0.4674
```

Xác suất:

```math
P(\pi/6<X<\pi/2)=\int_{\pi/6}^{\pi/2}0.5\sin xdx=0.4330
```

### Kết luận

`k=0.5`, `E(X)=1.5708`, `Var(X)=0.4674`, `P=0.4330`.

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

### Giải chi tiết

```math
\int_{-1}^{1}k(1-x^2)dx=1
```

```math
k\left[x-\frac{x^3}{3}\right]_{-1}^{1}=1
```

Tính cận:

```math
\left(1-\frac13\right)-\left(-1+\frac13\right)=\frac23-\left(-\frac23\right)=\frac43
```

```math
k\cdot\frac43=1\Rightarrow k=0.75
```

Kỳ vọng:

Miền đối xứng từ `-1` đến `1`, hàm mật độ cũng đối xứng. Phần âm và phần dương cân bằng nhau nên:

```math
E(X)=0
```

Moment bậc hai:

```math
E(X^2)=\int_{-1}^{1}x^2\cdot0.75(1-x^2)dx=0.2000
```

```math
Var(X)=0.2000-0^2=0.2000
```

Xác suất:

```math
P(-0.5<X<0.5)=\int_{-0.5}^{0.5}0.75(1-x^2)dx=0.6875
```

### Kết luận

`k=0.75`, `E(X)=0`, `Var(X)=0.2`, `P=0.6875`.

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

### Giải chi tiết

```math
\int_0^1k(2x+1)dx=1
```

```math
k[x^2+x]_0^1=1
```

```math
k(1+1)=1\Rightarrow k=0.5
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

`k=0.5`, `E(X)=0.5833`, `Var(X)=0.0764`, `P=0.5000`.

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

### Giải chi tiết

```math
\int_0^{+\infty}ke^{-x/2}dx=1
```

Vì:

```math
\int e^{-x/2}dx=-2e^{-x/2}
```

nên:

```math
\int_0^{+\infty}e^{-x/2}dx=2
```

```math
2k=1\Rightarrow k=0.5
```

Khi đó:

```math
f(x)=0.5e^{-x/2}
```

Đây là phân phối mũ với tham số `λ=0.5` vì dạng chuẩn là `λe^{-λx}`.

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

Nguyên hàm của `0.5e^{-x/2}` là `-e^{-x/2}`.

```math
P=[-e^{-x/2}]_1^4=e^{-1/2}-e^{-2}=0.4712
```

### Kết luận

`k=0.5`, `E(X)=2`, `Var(X)=4`, `P=0.4712`.

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

### Giải chi tiết

Tìm `k`:

```math
\int_0^{+\infty}kxe^{-x}dx=1
```

Ta có công thức tích phân Gamma:

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

`k=1`, `E(X)=2`, `Var(X)=2`, `P=0.5768`.

---

# MỤC 4. ƯỚC LƯỢNG VÀ KIỂM ĐỊNH THỐNG KÊ

## Khung tư duy chung

### Nhận diện kỳ vọng hay tỷ lệ

- Có `x̄`, `s`, `n` → bài về trung bình/kỳ vọng `μ`.
- Có `x` trường hợp đạt trong `n` mẫu → bài về tỷ lệ `p`.

### Vì sao khoảng tin cậy có dạng “ước lượng ± sai số”?

Ta không biết giá trị thật của tổng thể. Ta dùng mẫu để ước lượng. Nhưng mẫu có sai lệch, nên phải cộng/trừ sai số để tạo khoảng hợp lý.

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

### Nhận diện dạng

Đề cho trung bình mẫu `x̄` và độ lệch chuẩn mẫu `s`, nên đây là bài về kỳ vọng `μ`.

### Giải chi tiết

#### a. Ước lượng điểm

Ước lượng điểm tốt nhất cho `μ` là trung bình mẫu:

```math
\hat\mu=\bar x=168.5
```

#### b. Khoảng tin cậy 95%

Với 95%, lấy `z=1.96`.

Sai số:

```math
E=z\frac{s}{\sqrt n}=1.96\cdot\frac{7.2}{\sqrt{64}}=1.764
```

Khoảng tin cậy:

```math
168.5\pm1.764=[166.736;170.264]
```

#### c. Cỡ mẫu tối thiểu

Cỡ mẫu để sai số không vượt quá `d`:

```math
n\ge\left(\frac{zs}{d}\right)^2
```

```math
n\ge\left(\frac{1.96\cdot7.2}{1.5}\right)^2=88.47
```

Cỡ mẫu phải là số nguyên và phải đủ lớn, nên làm tròn lên:

```math
n=89
```

#### d. Kiểm định

Giả thuyết:

```math
H_0:\mu=170,\quad H_1:\mu<170
```

Thống kê kiểm định:

```math
Z=\frac{\bar x-\mu_0}{s/\sqrt n}=\frac{168.5-170}{7.2/\sqrt{64}}=-1.6667
```

Vì `H1` là dấu `<`, đây là kiểm định trái. Mức 5% bác bỏ nếu:

```math
Z<-1.645
```

Ta có `-1.6667<-1.645`, nên bác bỏ `H0`.

### Kết luận

- a. `168.5`.
- b. `[166.736;170.264]`.
- c. `n=89`.
- d. Có đủ cơ sở để kết luận chiều cao trung bình nhỏ hơn 170.

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

### Giải chi tiết

Ước lượng điểm:

```math
\hat\mu=12.4
```

Khoảng tin cậy 99%, dùng `z=2.576`:

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

Làm tròn lên:

```math
n=46
```

Kiểm định:

```math
Z=\frac{12.4-13}{2.1/\sqrt{36}}=-1.7143
```

Vì `H1: μ≠13`, đây là kiểm định hai phía. Bác bỏ nếu `|Z|>1.96`. Ở đây:

```math
|Z|=1.7143<1.96
```

nên không bác bỏ `H0`.

### Kết luận

- a. `12.4`.
- b. `[11.4984;13.3016]`.
- c. `n=46`.
- d. Chưa đủ cơ sở để kết luận thời gian xử lý trung bình khác 13.

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

### Giải chi tiết

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

Làm tròn lên:

```math
n=74
```

```math
Z=\frac{7.1-7.0}{1.3/\sqrt{100}}=0.7692
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `0.7692<1.645`, không bác bỏ `H0`.

### Kết luận

- a. `7.1`.
- b. `[6.8861;7.3139]`.
- c. `n=74`.
- d. Chưa đủ cơ sở để kết luận điểm trung bình lớn hơn 7.0.

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

### Giải chi tiết

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

```math
n=78
```

```math
Z=\frac{50.8-52}{4.5/\sqrt{49}}=-1.8667
```

Kiểm định trái, bác bỏ nếu `Z<-1.645`. Vì `-1.8667<-1.645`, bác bỏ `H0`.

### Kết luận

- a. `50.8`.
- b. `[49.5400;52.0600]`.
- c. `n=78`.
- d. Có đủ cơ sở để kết luận khối lượng trung bình nhỏ hơn 52.

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

### Giải chi tiết

```math
\hat\mu=9.6
```

Với 98%, `z=2.326`:

```math
E=2.326\cdot\frac{1.8}{\sqrt{81}}=0.4652
```

```math
CI=[9.1348;10.0652]
```

```math
n\ge\left(\frac{2.326\cdot1.8}{0.5}\right)^2=70.13
```

```math
n=71
```

```math
Z=\frac{9.6-9.2}{1.8/\sqrt{81}}=2.0000
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `2.0000>1.645`, bác bỏ `H0`.

### Kết luận

- a. `9.6`.
- b. `[9.1348;10.0652]`.
- c. `n=71`.
- d. Có đủ cơ sở để kết luận tuổi thọ pin trung bình lớn hơn 9.2.

---

## Bài 4.6. Tỷ lệ sản phẩm loại A

### Đề bài

Khảo sát 400 sản phẩm, có 52 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 95% cho tỷ lệ.  
c. Với độ chính xác `d = 0.03`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.1`, `H1: p > 0.1`.

### Nhận diện dạng

Đề cho số sản phẩm đạt đặc tính trên tổng số mẫu, nên đây là bài tỷ lệ.

### Giải chi tiết

Ước lượng điểm:

```math
\hat p=\frac{x}{n}=\frac{52}{400}=0.1300
```

Khoảng tin cậy 95%:

```math
E=1.96\sqrt{\frac{0.13(1-0.13)}{400}}=0.0330
```

```math
CI=[0.13-0.0330;0.13+0.0330]=[0.0970;0.1630]
```

Cỡ mẫu:

```math
n\ge\frac{1.96^2\cdot0.13\cdot0.87}{0.03^2}=482.84
```

```math
n=483
```

Kiểm định:

```math
Z=\frac{0.13-0.1}{\sqrt{0.1(1-0.1)/400}}=2.0000
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vậy bác bỏ `H0`.

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

### Giải chi tiết

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

```math
n=1121
```

```math
Z=\frac{0.12-0.15}{\sqrt{0.15\cdot0.85/625}}=-2.1004
```

Kiểm định trái, bác bỏ nếu `Z<-1.645`. Vậy bác bỏ `H0`.

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

### Giải chi tiết

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

```math
n=269
```

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

### Giải chi tiết

```math
\hat p=\frac{240}{1000}=0.2400
```

```math
E=1.96\sqrt{\frac{0.24\cdot0.76}{1000}}=0.0265
```

```math
CI=[0.2135;0.2665]
```

```math
n\ge\frac{1.96^2\cdot0.24\cdot0.76}{0.02^2}=1751.77
```

```math
n=1752
```

```math
Z=\frac{0.24-0.2}{\sqrt{0.2\cdot0.8/1000}}=3.1623
```

Kiểm định phải, bác bỏ nếu `Z>1.645`, nên bác bỏ `H0`.

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

### Giải chi tiết

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

```math
n=358
```

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

## Khung tư duy chung

Bài hồi quy có 3 việc:

1. Tính hệ số tương quan `r`.
2. Nhận xét quan hệ thuận/nghịch, mạnh/yếu.
3. Lập phương trình dự đoán `Ŷ=a+bX`.

Ý nghĩa:

- `r>0`: X tăng thì Y có xu hướng tăng.
- `r<0`: X tăng thì Y có xu hướng giảm.
- `|r|` càng gần 1 thì mối quan hệ tuyến tính càng mạnh.

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

### Giải chi tiết

Tính bằng công thức hồi quy hoặc máy thống kê cho kết quả:

```math
r=0.9982
```

Vì `r` dương và gần 1 nên chi phí quảng cáo và doanh thu có tương quan thuận rất mạnh.

Phương trình hồi quy:

```math
\hat Y=8.8571+5.6429X
```

Ý nghĩa hệ số `5.6429`: khi chi phí quảng cáo tăng 1 đơn vị, doanh thu dự đoán tăng trung bình khoảng 5.6429 đơn vị.

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

### Giải chi tiết

```math
r=0.9983
```

`r` dương gần 1, nên số giờ học và điểm thi có tương quan thuận rất mạnh.

```math
\hat Y=3.5714+0.6929X
```

Ý nghĩa: học thêm 1 giờ thì điểm dự đoán tăng trung bình khoảng `0.6929` điểm.

```math
\hat Y(8)=3.5714+0.6929\cdot8=9.1143
```

### Kết luận

- a. `r=0.9983`.
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

### Giải chi tiết

```math
r=0.9894
```

Nhiệt độ và lượng điện tiêu thụ có tương quan thuận rất mạnh.

```math
\hat Y=-2.8571+5.9143X
```

Ý nghĩa hệ số `5.9143`: nhiệt độ tăng 1 đơn vị thì điện tiêu thụ dự đoán tăng khoảng 5.9143 đơn vị.

```math
\hat Y(27)=-2.8571+5.9143\cdot27=156.8286
```

### Kết luận

- a. `r=0.9894`.
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

### Giải chi tiết

```math
r=0.9912
```

Tuổi máy càng cao thì chi phí bảo trì càng tăng, tương quan thuận rất mạnh.

```math
\hat Y=1.8667+2.8857X
```

```math
\hat Y(7)=1.8667+2.8857\cdot7=22.0667
```

### Kết luận

- a. `r=0.9912`.
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

### Giải chi tiết

```math
r=-0.9920
```

`r` âm gần -1 nên đây là tương quan nghịch rất mạnh. Giá tăng thì số lượng bán giảm.

```math
\hat Y=147.3333-4.7000X
```

Ý nghĩa: giá tăng 1 đơn vị thì số lượng bán dự đoán giảm khoảng 4.7 đơn vị.

```math
\hat Y(15)=147.3333-4.7\cdot15=76.8333
```

### Kết luận

- a. `r=-0.9920`.
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

### Giải chi tiết

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

- a. `r=0.9991`.
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

### Giải chi tiết

```math
r=0.9892
```

Độ ẩm và tỷ lệ lỗi có tương quan thuận rất mạnh.

```math
\hat Y=-3.0629+0.1646X
```

```math
\hat Y(48)=-3.0629+0.1646\cdot48=4.8371
```

### Kết luận

- a. `r=0.9892`.
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

### Giải chi tiết

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

- a. `r=0.9994`.
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

### Giải chi tiết

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

- a. `r=0.9949`.
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

### Giải chi tiết

```math
r=0.9977
```

Kinh nghiệm và lương tương quan thuận rất mạnh.

```math
\hat Y=6.1872+2.3498X
```

Ý nghĩa: kinh nghiệm tăng 1 năm thì lương dự đoán tăng trung bình khoảng 2.3498 triệu.

```math
\hat Y(7)=6.1872+2.3498\cdot7=22.6355
```

### Kết luận

- a. `r=0.9977`.
- b. `Ŷ=6.1872+2.3498X`.
- c. `Y(7)=22.6355`.

---

# CHECKLIST ÁP DỤNG TRONG PHÒNG THI

## 1. Bài xác suất nhiều nguồn

```text
Bước 1: Xác định các nguồn H1, H2, ...
Bước 2: Xác định xác suất chọn từng nguồn P(Hi)
Bước 3: Xác định xác suất kết quả trong từng nguồn P(A|Hi)
Bước 4: Cộng các tích P(Hi)P(A|Hi)
Bước 5: Nếu hỏi ngược nguồn, dùng Bayes
```

## 2. Bài tổ hợp

```text
Bước 1: Xác định tổng số cách
Bước 2: Xác định số cách thuận lợi
Bước 3: Lấy thuận lợi / tổng
Bước 4: Nếu có “ít nhất”, cân nhắc dùng biến cố đối
```

## 3. Bài chuẩn

```text
Bước 1: Lấy σ = căn phương sai
Bước 2: Chuẩn hóa từng cận
Bước 3: Tra bảng hoặc dùng máy
Bước 4: Nếu xác suất bên phải, đổi sang bên trái
```

## 4. Bài mật độ liên tục

```text
Bước 1: Tìm k từ ∫f(x)dx=1
Bước 2: Tính E(X)
Bước 3: Tính E(X²)
Bước 4: Tính Var(X)=E(X²)-[E(X)]²
Bước 5: Tính xác suất bằng tích phân theo cận đề bài
```

## 5. Bài ước lượng - kiểm định

```text
Bước 1: Nhận diện kỳ vọng hay tỷ lệ
Bước 2: Viết công thức khoảng tin cậy hoặc Z kiểm định
Bước 3: Thay số
Bước 4: So sánh ngưỡng
Bước 5: Kết luận bằng lời theo ngữ cảnh đề
```

## 6. Bài hồi quy

```text
Bước 1: Tính r
Bước 2: Nhận xét dấu và độ lớn của r
Bước 3: Lập Ŷ=a+bX
Bước 4: Thay X cần dự đoán
Bước 5: Diễn giải ý nghĩa hệ số b nếu cần
```
