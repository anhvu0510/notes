# HƯỚNG DẪN BẤM MÁY TÍNH CASIO FX-570 CHO XÁC SUẤT - THỐNG KÊ

> Mục tiêu file này: chỉ hướng dẫn **thao tác tổng quát trên máy tính Fx-570**, không liệt kê theo từng bài. Khi gặp bài cụ thể, đối chiếu dạng bài rồi áp dụng đúng quy trình.

Áp dụng tốt cho các dòng: **fx-570VN PLUS**, **fx-570ES PLUS**, **fx-570VN X**. Tên menu có thể hơi khác nhau giữa các dòng, nhưng logic bấm giống nhau.

---

# 1. Thiết lập máy trước khi làm bài

## 1.1. Reset khi máy bị sai mode hoặc nhớ biến cũ

```text
SHIFT → 9(CLR) → 3(All) → = → AC
```

Dùng khi:

- Kết quả ra lạ.
- Máy đang ở `STAT`, `TABLE`, `EQN` mà cần về tính thường.
- Đã lưu biến A, B, C trước đó và sợ bị lẫn.

## 1.2. Về chế độ tính thường

```text
MODE → 1(COMP)
```

Dùng cho phần xác suất, tổ hợp, phân phối chuẩn, kiểm định, tính công thức tay.

## 1.3. Chọn hiển thị thập phân

Nếu kết quả ra phân số nhưng muốn xem số thập phân:

```text
S⇔D
```

Nếu muốn cố định số chữ số thập phân:

```text
SHIFT → MODE(SETUP) → Fix → chọn số chữ số
```

Ví dụ chọn `4` để làm tròn 4 chữ số.

---

# 2. Các phím nền tảng hay dùng

## 2.1. Tổ hợp `nCr`

Dùng cho bài chọn, rút bi, rút bài, lấy mẫu không hoàn lại, không xét thứ tự.

```text
n → SHIFT → ÷(nCr) → r → =
```

Ví dụ tính `C(20,4)`:

```text
20 → SHIFT → ÷(nCr) → 4 → =
```

Mẹo nhận diện: đề có các chữ **chọn**, **lấy đồng thời**, **rút cùng lúc**, **lập nhóm** thì thường dùng `nCr`.

## 2.2. Chỉnh hợp `nPr`

Dùng khi có xét thứ tự, vai trò khác nhau, xếp vị trí.

```text
n → SHIFT → ×(nPr) → r → =
```

Mẹo nhận diện: đề có **xếp**, **phân công chức vụ**, **thứ tự**, **mã số**, **số có các chữ số khác nhau** thì có thể dùng `nPr` hoặc quy tắc nhân.

## 2.3. Giai thừa `!`

```text
n → SHIFT → x⁻¹(!) → =
```

Dùng trong hoán vị, bài xếp toàn bộ `n` phần tử.

## 2.4. Lũy thừa

```text
a → x^□ → b → =
```

Ví dụ `0.4^5`:

```text
0.4 → x^□ → 5 → =
```

## 2.5. Căn bậc hai

```text
√ → biểu thức → =
```

Dùng nhiều trong thống kê:

```text
s÷√n
√(p×(1-p)÷n)
```

## 2.6. Lưu kết quả vào biến nhớ

Sau khi tính ra kết quả cần dùng lại:

```text
kết_quả → SHIFT → RCL(STO) → A
```

Gọi lại biến A:

```text
ALPHA → A
```

Nên dùng biến nhớ khi:

- Tính Bayes, vì mẫu số dùng lại nhiều lần.
- Tính kỳ vọng, phương sai.
- Tính hồi quy rồi dự đoán.

---

# 3. Bấm dạng xác suất cổ điển bằng tổ hợp

## 3.1. Công thức gốc

```text
P = số_cách_thuận_lợi ÷ số_cách_tất_cả
```

## 3.2. Quy trình bấm chuẩn

```text
Bước 1: Xác định tổng số cách.
Bước 2: Xác định số cách thuận lợi.
Bước 3: Nhập thuận_lợi ÷ tổng =
Bước 4: S⇔D nếu cần ra số thập phân.
```

## 3.3. Mẫu bấm tổng quát

### Rút đúng k phần tử loại A trong n phần tử lấy m phần tử

Giả sử có `a` phần tử loại A, `b` phần tử loại khác, lấy `m` phần tử, cần đúng `k` loại A:

```text
[(a nCr k) × (b nCr (m-k))] ÷ [(a+b) nCr m] =
```

### Ít nhất 1 phần tử loại A

Dùng biến cố đối để bấm nhanh:

```text
1 - [(số_không_phải_A nCr m) ÷ (tổng nCr m)] =
```

### Ít nhất k phần tử loại A

Cộng từng trường hợp:

```text
[(a nCr k)(b nCr m-k) + (a nCr k+1)(b nCr m-k-1) + ...] ÷ [(a+b) nCr m] =
```

Mẹo: nếu số trường hợp quá nhiều, thử dùng biến cố đối.

---

# 4. Bấm xác suất đầy đủ và Bayes

## 4.1. Dạng nhận diện

Đề thường có nhiều nguồn:

- Nhiều hộp.
- Nhiều dây chuyền.
- Nhiều phân xưởng.
- Nhiều nhóm người.
- Nhiều loại sản phẩm.

Sau đó chọn ngẫu nhiên 1 nguồn rồi quan sát kết quả.

## 4.2. Bấm xác suất đầy đủ

Công thức:

```text
P(A)=P(H1)P(A|H1)+P(H2)P(A|H2)+...+P(Hn)P(A|Hn)
```

Thao tác:

```text
P(H1) × P(A|H1) + P(H2) × P(A|H2) + ... =
```

Sau khi ra kết quả, nên lưu vào A:

```text
Ans → SHIFT → RCL(STO) → A
```

## 4.3. Bấm Bayes

Công thức:

```text
P(Hi|A)=P(Hi)P(A|Hi) ÷ P(A)
```

Nếu đã lưu `P(A)` vào biến A:

```text
[P(Hi) × P(A|Hi)] ÷ ALPHA A =
```

## 4.4. Mẹo chống nhầm

- Mẫu số Bayes luôn là xác suất của dữ kiện đã biết sau chữ **biết rằng**.
- Tử số là đúng nhánh vừa thỏa nguồn cần hỏi vừa thỏa dữ kiện đã biết.
- Nếu đề hỏi “biết sản phẩm lỗi, xác suất do phân xưởng C” thì mẫu số là xác suất lỗi, không phải xác suất phân xưởng C.

---

# 5. Bấm xác suất nhị thức

## 5.1. Dạng nhận diện

Một phép thử lặp `n` lần độc lập, mỗi lần có xác suất thành công `p`.

Công thức:

```text
P(X=k)=C(n,k) × p^k × (1-p)^(n-k)
```

## 5.2. Bấm đúng k lần thành công

```text
(n nCr k) × p^k × (1-p)^(n-k) =
```

## 5.3. Bấm ít nhất 1 lần thành công

Dùng biến cố đối:

```text
1 - (1-p)^n =
```

## 5.4. Bấm ít nhất k lần thành công

Cộng từ `k` đến `n`:

```text
Σ C(n,i) p^i (1-p)^(n-i), i=k..n
```

Nếu máy có tổng sigma `Σ`, có thể dùng. Nếu không, bấm từng hạng rồi cộng.

Mẹo: với `ít nhất 1`, `không có lần nào`, `nhiều nhất 1`, nên dùng biến cố đối để nhanh.

---

# 6. Bấm phân phối chuẩn trên Fx-570

## 6.1. Dạng nhận diện

Đề ghi:

```text
X ~ N(μ, σ²)
```

Nhớ: số thứ hai là **phương sai**. Phải lấy căn để được độ lệch chuẩn:

```text
σ = √σ²
```

## 6.2. Chuẩn hóa Z

Công thức:

```text
Z = (X - μ) ÷ σ
```

Bấm:

```text
(x - μ) ÷ σ =
```

## 6.3. Nếu máy có menu DIST

### Tính `P(a < X < b)` bằng Normal CD

```text
MODE → DIST → Normal CD
Lower = a
Upper = b
σ = độ_lệch_chuẩn
μ = trung_bình
=
```

### Tìm T nếu biết `P(X<T)=p`

```text
MODE → DIST → Inverse Normal / InvN
Area = p
σ = độ_lệch_chuẩn
μ = trung_bình
=
```

### Tìm T nếu biết `P(X>T)=p`

Đổi về bên trái:

```text
Area = 1 - p
```

Rồi dùng `InvN`.

## 6.4. Nếu máy không có DIST

Làm theo 2 bước:

```text
Bước 1: Tính Z1=(a-μ)/σ, Z2=(b-μ)/σ bằng máy.
Bước 2: Tra bảng chuẩn tắc Φ(Z).
Bước 3: P(a<X<b)=Φ(Z2)-Φ(Z1).
```

## 6.5. Mốc Z hay gặp

| Xác suất bên trái | z |
|---:|---:|
| 0.90 | 1.2816 |
| 0.95 | 1.6449 |
| 0.975 | 1.9600 |
| 0.99 | 2.3263 |
| 0.10 | -1.2816 |
| 0.05 | -1.6449 |
| 0.025 | -1.9600 |

---

# 7. Bấm tích phân cho BNN liên tục 1 biến

## 7.1. Dạng nhận diện

Đề cho hàm mật độ:

```text
f(x)=k.g(x), a<x<b
```

Cần tìm `k`, kỳ vọng, phương sai, xác suất.

## 7.2. Tìm k

Vì tổng xác suất bằng 1:

```text
k = 1 ÷ ∫ g(x) dx từ a đến b
```

Thao tác:

```text
1 ÷ ∫(g(X), a, b) =
```

Lưu kết quả vào A:

```text
Ans → SHIFT → RCL(STO) → A
```

## 7.3. Tính kỳ vọng E(X)

```text
∫(X × A × g(X), a, b) =
```

Lưu kết quả vào B:

```text
Ans → SHIFT → RCL(STO) → B
```

## 7.4. Tính E(X²)

```text
∫(X² × A × g(X), a, b) =
```

Lưu vào C nếu cần.

## 7.5. Tính phương sai

```text
E(X²) - [E(X)]² =
```

Nếu đã lưu `E(X)` vào B:

```text
E_X2 - (ALPHA B)^2 =
```

## 7.6. Tính xác suất `P(c<X<d)`

```text
∫(A × g(X), c, d) =
```

## 7.7. Nhập biến X và hàm mũ

Biến X:

```text
ALPHA → phím có chữ X
```

Hàm mũ `e^x`:

```text
SHIFT → ln(e^x)
```

Số pi:

```text
SHIFT → EXP(π)
```

## 7.8. Cận vô cực

Fx-570 thường không nhập trực tiếp `∞`. Với hàm mũ giảm nhanh, thay bằng số lớn:

```text
0 đến 50
```

hoặc

```text
0 đến 100
```

Ví dụ `e^(-x)` từ `0` đến `∞` thì nhập `0` đến `50` thường đã đủ chính xác.

---

# 8. Bấm ước lượng khoảng cho kỳ vọng

## 8.1. Dạng nhận diện

Đề cho:

```text
n, x̄, s
```

và yêu cầu khoảng tin cậy cho kỳ vọng `μ`.

## 8.2. Công thức

```text
x̄ ± z × s ÷ √n
```

## 8.3. Bấm sai số

```text
z × s ÷ √n =
```

Lưu sai số vào A nếu muốn:

```text
Ans → STO → A
```

## 8.4. Bấm cận dưới và cận trên

```text
x̄ - A =
x̄ + A =
```

## 8.5. Mốc z cho khoảng tin cậy

| Độ tin cậy | z |
|---:|---:|
| 90% | 1.645 |
| 95% | 1.960 |
| 98% | 2.326 |
| 99% | 2.576 |

---

# 9. Bấm ước lượng khoảng cho tỷ lệ

## 9.1. Dạng nhận diện

Đề cho:

```text
n quan sát, có x trường hợp đạt đặc tính A
```

Khi đó:

```text
p̂ = x ÷ n
```

## 9.2. Bấm p mũ

```text
x ÷ n =
```

Lưu vào A:

```text
Ans → STO → A
```

## 9.3. Bấm sai số

```text
z × √(A × (1 - A) ÷ n) =
```

Lưu sai số vào B.

## 9.4. Bấm khoảng tin cậy

```text
A - B =
A + B =
```

---

# 10. Bấm cỡ mẫu

## 10.1. Cỡ mẫu cho kỳ vọng

Công thức:

```text
n ≥ (z × s ÷ d)^2
```

Bấm:

```text
(z × s ÷ d)^2 =
```

Sau đó **làm tròn lên**.

Ví dụ ra `88.47` thì lấy `n=89`.

## 10.2. Cỡ mẫu cho tỷ lệ

Nếu có tỷ lệ ước lượng `p̂`:

```text
n ≥ z² × p̂ × (1-p̂) ÷ d²
```

Nếu chưa có `p̂`, lấy an toàn:

```text
p̂ = 0.5
```

Bấm:

```text
z^2 × p × (1-p) ÷ d^2 =
```

Sau đó làm tròn lên.

---

# 11. Bấm kiểm định kỳ vọng 1 mẫu

## 11.1. Dạng nhận diện

Đề có:

```text
H0: μ = μ0
H1: μ > μ0 hoặc μ < μ0 hoặc μ ≠ μ0
```

## 11.2. Bấm thống kê kiểm định

```text
Z = (x̄ - μ0) ÷ (s ÷ √n)
```

Thao tác:

```text
(xbar - mu0) ÷ (s ÷ √n) =
```

## 11.3. So sánh mức ý nghĩa 5%

| Đối thuyết H1 | Bác bỏ H0 nếu |
|---|---|
| `μ > μ0` | `Z > 1.645` |
| `μ < μ0` | `Z < -1.645` |
| `μ ≠ μ0` | `|Z| > 1.96` |

## 11.4. Cách kết luận

Không chỉ ghi “bác bỏ H0”. Nên ghi:

```text
Ở mức ý nghĩa 5%, có/không có đủ cơ sở để kết luận ... theo nội dung đề bài.
```

---

# 12. Bấm kiểm định tỷ lệ 1 mẫu

## 12.1. Dạng nhận diện

Đề có:

```text
x trường hợp đạt trên n quan sát
H0: p = p0
```

## 12.2. Bấm p mũ

```text
p̂ = x ÷ n
```

## 12.3. Bấm thống kê kiểm định

```text
Z = (p̂ - p0) ÷ √(p0 × (1-p0) ÷ n)
```

Thao tác:

```text
(p_hat - p0) ÷ √(p0 × (1-p0) ÷ n) =
```

## 12.4. So sánh

Giống kiểm định kỳ vọng:

| Đối thuyết H1 | Bác bỏ H0 nếu |
|---|---|
| `p > p0` | `Z > 1.645` |
| `p < p0` | `Z < -1.645` |
| `p ≠ p0` | `|Z| > 1.96` |

---

# 13. Bấm tương quan và hồi quy tuyến tính

## 13.1. Vào mode thống kê hồi quy

```text
MODE → STAT → A+BX
```

Dòng `A+BX` nghĩa là máy sẽ fit phương trình:

```text
Y = A + B X
```

## 13.2. Nhập dữ liệu

Nhập từng dòng:

```text
X → = → Y → =
```

hoặc nhập vào bảng theo cột X, Y tùy dòng máy.

Sau khi nhập hết dữ liệu, kiểm tra số dòng để tránh thiếu dòng.

## 13.3. Lấy hệ số A

```text
SHIFT → 1(STAT) → Reg → A → =
```

## 13.4. Lấy hệ số B

```text
SHIFT → 1(STAT) → Reg → B → =
```

## 13.5. Lấy hệ số tương quan r

```text
SHIFT → 1(STAT) → Reg → r → =
```

## 13.6. Dự đoán Y tại X=x0

Cách thủ công:

```text
A + B × x0 =
```

Cách dùng chức năng dự đoán nếu máy có:

```text
x0 → SHIFT → 1(STAT) → Reg → ŷ → =
```

## 13.7. Xóa dữ liệu STAT cũ

Trước khi nhập bài mới:

```text
SHIFT → 9(CLR) → 1(Setup/Data tùy máy) → =
```

Hoặc reset toàn bộ nếu cần:

```text
SHIFT → 9 → 3 → = → AC
```

---

# 14. Mẹo chọn đúng thao tác máy theo dạng đề

| Dạng đề | Thao tác máy nên dùng |
|---|---|
| Rút bi, rút bài, chọn nhóm | `nCr` |
| Xếp người, phân chức vụ | `nPr`, giai thừa, quy tắc nhân |
| Ít nhất 1 | `1 - xác suất không có` |
| Nhiều nguồn/hộp/phân xưởng | Tính tổng các nhánh, lưu mẫu vào A |
| Biết rằng đã xảy ra | Bayes: tử số nhánh đúng / mẫu số đã lưu |
| Phân phối chuẩn | `Normal CD`, `InvN`, hoặc chuẩn hóa Z |
| Hàm mật độ liên tục | Tích phân `∫dx` |
| Khoảng tin cậy kỳ vọng | `z×s÷√n` |
| Khoảng tin cậy tỷ lệ | `z×√(p(1-p)/n)` |
| Kiểm định | Tính Z rồi so mốc tới hạn |
| Tương quan hồi quy | `MODE → STAT → A+BX` |

---

# 15. Lỗi bấm máy hay gặp

1. **Quên đóng ngoặc** khi nhập biểu thức dài.
2. **Nhầm phương sai với độ lệch chuẩn** trong phân phối chuẩn.
3. **Không reset STAT** nên dữ liệu bài trước còn trong máy.
4. **Dùng nPr thay vì nCr** trong bài rút/chọn không xét thứ tự.
5. **Quên đổi P(X>T)** thành `Area = 1 - p` khi dùng `InvN`.
6. **Quên làm tròn lên** khi tính cỡ mẫu.
7. **Nhập sai dấu đối thuyết** nên so sánh sai ngưỡng kiểm định.
8. **Tính Var(X) thành E(X²)-E(X)** thay vì `E(X²)-[E(X)]²`.

---

# 16. Checklist thao tác khi làm bài thi

```text
[ ] Reset hoặc về COMP nếu cần.
[ ] Xác định đúng dạng bài.
[ ] Ghi công thức ra giấy trước khi bấm.
[ ] Bấm từng phần nhỏ, lưu biến nếu biểu thức dài.
[ ] Kiểm tra đơn vị: σ hay σ², p hay %, n hay x.
[ ] Kết quả xác suất phải nằm trong [0,1].
[ ] Kết quả cỡ mẫu phải làm tròn lên.
[ ] Hồi quy phải reset dữ liệu STAT trước bài mới.
```
