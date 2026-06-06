# MỤC 4 - BÀI GIẢI CHI TIẾT: ƯỚC LƯỢNG VÀ KIỂM ĐỊNH THỐNG KÊ

> File này tách riêng Mục 4. Mỗi bài có đề, nhận diện kỳ vọng/tỷ lệ, công thức, thay số từng bước, kết luận kiểm định bằng lời.

---

# Khung tư duy Mục 4

## 1. Nhận diện bài kỳ vọng hay tỷ lệ

```text
Có n, x̄, s  → bài kỳ vọng μ
Có n mẫu và x trường hợp đạt → bài tỷ lệ p
```

## 2. Khoảng tin cậy cho kỳ vọng

```math
\bar x\pm z\frac{s}{\sqrt n}
```

Trong đó:

```text
x̄ = trung bình mẫu
s = độ lệch chuẩn mẫu
n = cỡ mẫu
z = mốc chuẩn theo độ tin cậy
```

## 3. Khoảng tin cậy cho tỷ lệ

```math
\hat p\pm z\sqrt{\frac{\hat p(1-\hat p)}{n}}
```

## 4. Cỡ mẫu

Cho kỳ vọng:

```math
n\ge\left(\frac{zs}{d}\right)^2
```

Cho tỷ lệ:

```math
n\ge\frac{z^2\hat p(1-\hat p)}{d^2}
```

Cỡ mẫu luôn **làm tròn lên**.

## 5. Kiểm định mức ý nghĩa 5%

Kiểm định trái:

```math
H_1:<,\quad \text{bác bỏ nếu } Z<-1.645
```

Kiểm định phải:

```math
H_1:>,\quad \text{bác bỏ nếu } Z>1.645
```

Kiểm định hai phía:

```math
H_1:\ne,\quad \text{bác bỏ nếu } |Z|>1.96
```

---

# Bài 4.1. Trung bình chiều cao

## Đề bài

Khảo sát 64 quan sát về chiều cao, thu được:

- `n = 64`
- `x̄ = 168.5`
- `s = 7.2`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 95% cho kỳ vọng.  
c. Với độ chính xác `d = 1.5`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 170`, `H1: μ < 170`.

## Nhận diện dạng

Có `x̄`, `s`, `n`, nên đây là bài kỳ vọng tổng thể `μ`.

## Giải từng bước

### a. Ước lượng điểm

Ước lượng điểm cho kỳ vọng là trung bình mẫu:

```math
\hat\mu=\bar x=168.5
```

### b. Khoảng tin cậy 95%

Với 95%, dùng:

```math
z=1.96
```

Sai số:

```math
E=z\frac{s}{\sqrt n}=1.96\frac{7.2}{\sqrt{64}}
```

```math
E=1.96\frac{7.2}{8}=1.764
```

Khoảng tin cậy:

```math
CI=168.5\pm1.764=[166.736;170.264]
```

### c. Cỡ mẫu

Công thức:

```math
n\ge\left(\frac{zs}{d}\right)^2
```

```math
n\ge\left(\frac{1.96\cdot7.2}{1.5}\right)^2=88.47
```

Làm tròn lên:

```math
n=89
```

### d. Kiểm định

Giả thuyết:

```math
H_0:\mu=170,\quad H_1:\mu<170
```

Thống kê kiểm định:

```math
Z=\frac{\bar x-\mu_0}{s/\sqrt n}=\frac{168.5-170}{7.2/\sqrt{64}}
```

```math
Z=-1.6667
```

Vì `H1` có dấu `<`, đây là kiểm định trái. Bác bỏ nếu:

```math
Z<-1.645
```

Ta có:

```math
-1.6667<-1.645
```

nên bác bỏ `H0`.

## Kết luận

```text
a/ 168.5
b/ [166.736;170.264]
c/ n=89
d/ Có đủ cơ sở để kết luận μ<170.
```

---

# Bài 4.2. Thời gian xử lý

## Đề bài

Khảo sát 36 quan sát về thời gian xử lý, thu được:

- `n = 36`
- `x̄ = 12.4`
- `s = 2.1`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 99% cho kỳ vọng.  
c. Với độ chính xác `d = 0.8`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 13`, `H1: μ ≠ 13`.

## Giải từng bước

Ước lượng điểm:

```math
\hat\mu=\bar x=12.4
```

Khoảng tin cậy 99%, dùng `z=2.576`:

```math
E=2.576\frac{2.1}{\sqrt{36}}=2.576\frac{2.1}{6}=0.9016
```

```math
CI=12.4\pm0.9016=[11.4984;13.3016]
```

Cỡ mẫu:

```math
n\ge\left(\frac{2.576\cdot2.1}{0.8}\right)^2=45.69
```

```math
n=46
```

Kiểm định:

```math
H_0:\mu=13,\quad H_1:\mu\ne13
```

```math
Z=\frac{12.4-13}{2.1/\sqrt{36}}=-1.7143
```

Hai phía, bác bỏ nếu `|Z|>1.96`. Vì:

```math
|-1.7143|=1.7143<1.96
```

nên không bác bỏ `H0`.

## Kết luận

```text
a/ 12.4
b/ [11.4984;13.3016]
c/ n=46
d/ Chưa đủ cơ sở để kết luận μ≠13.
```

---

# Bài 4.3. Điểm thi

## Đề bài

Khảo sát 100 quan sát về điểm thi, thu được:

- `n = 100`
- `x̄ = 7.1`
- `s = 1.3`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 90% cho kỳ vọng.  
c. Với độ chính xác `d = 0.25`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 7.0`, `H1: μ > 7.0`.

## Giải từng bước

```math
\hat\mu=7.1
```

Với 90%, `z=1.645`:

```math
E=1.645\frac{1.3}{\sqrt{100}}=0.2139
```

```math
CI=7.1\pm0.2139=[6.8861;7.3139]
```

Cỡ mẫu:

```math
n\ge\left(\frac{1.645\cdot1.3}{0.25}\right)^2=73.18
```

```math
n=74
```

Kiểm định:

```math
Z=\frac{7.1-7.0}{1.3/\sqrt{100}}=0.7692
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `0.7692<1.645`, không bác bỏ `H0`.

## Kết luận

```text
a/ 7.1
b/ [6.8861;7.3139]
c/ n=74
d/ Chưa đủ cơ sở để kết luận μ>7.0.
```

---

# Bài 4.4. Khối lượng sản phẩm

## Đề bài

Khảo sát 49 quan sát về khối lượng, thu được:

- `n = 49`
- `x̄ = 50.8`
- `s = 4.5`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 95% cho kỳ vọng.  
c. Với độ chính xác `d = 1.0`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 52`, `H1: μ < 52`.

## Giải từng bước

```math
\hat\mu=50.8
```

```math
E=1.96\frac{4.5}{\sqrt{49}}=1.96\frac{4.5}{7}=1.26
```

```math
CI=[50.8-1.26;50.8+1.26]=[49.5400;52.0600]
```

```math
n\ge\left(\frac{1.96\cdot4.5}{1.0}\right)^2=77.79\Rightarrow n=78
```

```math
Z=\frac{50.8-52}{4.5/\sqrt{49}}=-1.8667
```

Kiểm định trái, bác bỏ nếu `Z<-1.645`. Vì `-1.8667<-1.645`, bác bỏ `H0`.

## Kết luận

```text
a/ 50.8
b/ [49.5400;52.0600]
c/ n=78
d/ Có đủ cơ sở để kết luận μ<52.
```

---

# Bài 4.5. Tuổi thọ pin

## Đề bài

Khảo sát 81 quan sát về tuổi thọ pin, thu được:

- `n = 81`
- `x̄ = 9.6`
- `s = 1.8`

Yêu cầu:

a. Ước lượng điểm cho kỳ vọng tổng thể.  
b. Lập khoảng tin cậy 98% cho kỳ vọng.  
c. Với độ chính xác `d = 0.5`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: μ = 9.2`, `H1: μ > 9.2`.

## Giải từng bước

```math
\hat\mu=9.6
```

Với 98%, `z=2.326`:

```math
E=2.326\frac{1.8}{\sqrt{81}}=0.4652
```

```math
CI=[9.6-0.4652;9.6+0.4652]=[9.1348;10.0652]
```

```math
n\ge\left(\frac{2.326\cdot1.8}{0.5}\right)^2=70.13\Rightarrow n=71
```

```math
Z=\frac{9.6-9.2}{1.8/\sqrt{81}}=2.0000
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `2.0000>1.645`, bác bỏ `H0`.

## Kết luận

```text
a/ 9.6
b/ [9.1348;10.0652]
c/ n=71
d/ Có đủ cơ sở để kết luận μ>9.2.
```

---

# Bài 4.6. Tỷ lệ sản phẩm loại A

## Đề bài

Khảo sát 400 sản phẩm, có 52 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 95% cho tỷ lệ.  
c. Với độ chính xác `d = 0.03`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.1`, `H1: p > 0.1`.

## Nhận diện dạng

Có `x=52` sản phẩm đạt trong `n=400`, nên đây là bài tỷ lệ.

## Giải từng bước

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
H_0:p=0.1,\quad H_1:p>0.1
```

```math
Z=\frac{0.13-0.1}{\sqrt{0.1(1-0.1)/400}}=2.0000
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Vì `2.0000>1.645`, bác bỏ `H0`.

## Kết luận

```text
a/ p̂=0.1300
b/ [0.0970;0.1630]
c/ n=483
d/ Có đủ cơ sở để kết luận p>0.1.
```

---

# Bài 4.7. Tỷ lệ lỗi khảo sát 625 mẫu

## Đề bài

Khảo sát 625 sản phẩm, có 75 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 99% cho tỷ lệ.  
c. Với độ chính xác `d = 0.025`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.15`, `H1: p < 0.15`.

## Giải từng bước

```math
\hat p=\frac{75}{625}=0.1200
```

Với 99%, `z=2.576`:

```math
E=2.576\sqrt{\frac{0.12\cdot0.88}{625}}=0.0335
```

```math
CI=[0.12-0.0335;0.12+0.0335]=[0.0865;0.1535]
```

```math
n\ge\frac{2.576^2\cdot0.12\cdot0.88}{0.025^2}=1120.82\Rightarrow n=1121
```

```math
Z=\frac{0.12-0.15}{\sqrt{0.15\cdot0.85/625}}=-2.1004
```

Kiểm định trái, bác bỏ nếu `Z<-1.645`. Bác bỏ `H0`.

## Kết luận

```text
a/ p̂=0.1200
b/ [0.0865;0.1535]
c/ n=1121
d/ Có đủ cơ sở để kết luận p<0.15.
```

---

# Bài 4.8. Khảo sát 300 mẫu

## Đề bài

Khảo sát 300 sản phẩm, có 138 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 90% cho tỷ lệ.  
c. Với độ chính xác `d = 0.05`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.5`, `H1: p ≠ 0.5`.

## Giải từng bước

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
n\ge\frac{1.645^2\cdot0.46\cdot0.54}{0.05^2}=268.89\Rightarrow n=269
```

```math
Z=\frac{0.46-0.5}{\sqrt{0.5\cdot0.5/300}}=-1.3856
```

Kiểm định hai phía, bác bỏ nếu `|Z|>1.96`. Vì `1.3856<1.96`, không bác bỏ `H0`.

## Kết luận

```text
a/ p̂=0.4600
b/ [0.4127;0.5073]
c/ n=269
d/ Chưa đủ cơ sở để kết luận p≠0.5.
```

---

# Bài 4.9. Khảo sát 1000 mẫu

## Đề bài

Khảo sát 1000 sản phẩm, có 240 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 95% cho tỷ lệ.  
c. Với độ chính xác `d = 0.02`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.2`, `H1: p > 0.2`.

## Giải từng bước

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
n\ge\frac{1.96^2\cdot0.24\cdot0.76}{0.02^2}=1751.77\Rightarrow n=1752
```

```math
Z=\frac{0.24-0.2}{\sqrt{0.2\cdot0.8/1000}}=3.1623
```

Kiểm định phải, bác bỏ nếu `Z>1.645`. Bác bỏ `H0`.

## Kết luận

```text
a/ p̂=0.2400
b/ [0.2135;0.2665]
c/ n=1752
d/ Có đủ cơ sở để kết luận p>0.2.
```

---

# Bài 4.10. Khảo sát 250 mẫu

## Đề bài

Khảo sát 250 sản phẩm, có 30 sản phẩm mang đặc tính A.

Yêu cầu:

a. Tìm ước lượng điểm cho tỷ lệ `p`.  
b. Lập khoảng tin cậy 98% cho tỷ lệ.  
c. Với độ chính xác `d = 0.04`, cần cỡ mẫu tối thiểu bao nhiêu?  
d. Kiểm định mức ý nghĩa 5%: `H0: p = 0.1`, `H1: p ≠ 0.1`.

## Giải từng bước

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
n\ge\frac{2.326^2\cdot0.12\cdot0.88}{0.04^2}=357.11\Rightarrow n=358
```

```math
Z=\frac{0.12-0.1}{\sqrt{0.1\cdot0.9/250}}=1.0541
```

Kiểm định hai phía, bác bỏ nếu `|Z|>1.96`. Vì `1.0541<1.96`, không bác bỏ `H0`.

## Kết luận

```text
a/ p̂=0.1200
b/ [0.0722;0.1678]
c/ n=358
d/ Chưa đủ cơ sở để kết luận p≠0.1.
```
