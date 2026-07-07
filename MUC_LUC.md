# MỤC LỤC TRA CỨU — Thuật toán & Phương pháp (Week 1 → Week 15)

> File tra cứu nhanh: cần biết một thuật toán/phương pháp nằm ở **notebook nào, câu nào, cell nào** thì đọc file này.
> Gồm 2 phần: **[A. Bảng tra A–Z](#a-bảng-tra-a–z)** (tra nhanh theo tên) và **[B. Chi tiết theo tuần](#b-chi-tiết-theo-tuần)** (đi tuần tự từng notebook).
>
> Ghi chú cell: đánh số cell bắt đầu từ 0 theo thứ tự trong notebook. Hàm ghi dạng `ten_ham()`.

---

## A. Bảng tra A–Z

### A.1 Tìm nghiệm phương trình / hệ phi tuyến

| Phương pháp | Tuần | File | Câu / Vị trí | Hàm chính |
|---|---|---|---|---|
| Chia đôi (Bisection) | 2 | [Week2.ipynb](Week2.ipynb) | mục "Phương pháp Chia Đôi" (cell 12) | `bisection()` (cell 8, 11, 14) |
| Dây cung (Chord) | 3 | [Week3.ipynb](Week3.ipynb) | Câu 7, 8, 9, 10, 11 | `bisect_chord()`, `day_cung()` |
| Tiếp tuyến Newton (vô hướng) | 3 | [Week3.ipynb](Week3.ipynb) | Câu 7, 8, 9, 10, 11 | `newton()` |
| Tính căn bậc n | 3 | [Week3.ipynb](Week3.ipynb) | Câu 9 (cell 15–16) | `tinh_can()`, `day_cung()`, `newton()` |
| Lặp đơn (vô hướng) | 4 | [Week4.ipynb](Week4.ipynb) | Câu 12–13 | `lap_don()`, `phi()` |
| Lặp đơn giải hệ phi tuyến | 5 | [Week5.ipynb](Week5.ipynb) | Câu 15 | `lap_don()`, `phi()` |
| Newton giải hệ phi tuyến (Jacobi) | 5 | [Week5.ipynb](Week5.ipynb) | Câu 16 | `newton_N()`, `newton_eps()` |

### A.2 Hệ tuyến tính — Phương pháp trực tiếp

| Phương pháp | Tuần | File | Câu / Vị trí | Hàm chính |
|---|---|---|---|---|
| Khử Gauss (quy trình thuận) | 6 | [Week6.ipynb](Week6.ipynb) | Câu 23, 25 | `gauss_solve()` |
| Thế ngược (quy trình ngược) | 6 | [Week6.ipynb](Week6.ipynb) | Câu 24 | (trong `gauss_solve()`) |
| Gauss có chọn phần tử chủ (pivoting) | 6 | [Week6.ipynb](Week6.ipynb) | mục 2 (cell 5) | `gauss_solve()` |
| Gauss-Jordan | 6 | [Week6.ipynb](Week6.ipynb) | mục 3 (cell 5–6) | `gauss_jordan()` |
| Phân tách LU (Doolittle) | 7 | [Week7.ipynb](Week7.ipynb) | Câu 27 | `lu_decompose()` |
| Giải AX=B bằng LU | 7 | [Week7.ipynb](Week7.ipynb) | Câu 28 | `lu_solve()`, `forward_sub()`, `backward_sub()` |
| Phân tách Cholesky | 7 | [Week7.ipynb](Week7.ipynb) | Câu 29 | `cholesky_decompose()` |
| Giải AX=B bằng Cholesky | 7 | [Week7.ipynb](Week7.ipynb) | Câu 30 | `cholesky_solve()` |

### A.3 Hệ tuyến tính — Phương pháp lặp

| Phương pháp | Tuần | File | Câu / Vị trí | Hàm chính |
|---|---|---|---|---|
| Lặp đơn (x = Bx + g) | 8 | [Week8.ipynb](Week8.ipynb) | Câu 31, 34, 36a | `lap_don()` |
| Lặp Jacobi | 8 | [Week8.ipynb](Week8.ipynb) | Câu 32, 36b | `jacobi()` |
| (LU dùng lại trong bài lặp) | 8 | [Week8.ipynb](Week8.ipynb) | Câu 33, 35 | `lu_solve()` |
| Lặp Gauss-Seidel | 9 | [Week9.ipynb](Week9.ipynb) | Câu 37, 38 | `gauss_seidel()` |
| Lặp Seidel (x = Bx + d) | 9 | [Week9.ipynb](Week9.ipynb) | Câu 39 | `seidel()` |

### A.4 Ma trận nghịch đảo

| Phương pháp | Tuần | File | Câu / Vị trí | Hàm chính |
|---|---|---|---|---|
| Nghịch đảo bằng Gauss-Jordan | 10–11 | [Week10-11.ipynb](Week10-11.ipynb) | Câu 39 | `inv_gauss_jordan()` |
| Nghịch đảo bằng Cholesky | 10–11 | [Week10-11.ipynb](Week10-11.ipynb) | Câu 40 | `inv_cholesky()` |
| Nghịch đảo bằng viền quanh (bordering) | 10–11 | [Week10-11.ipynb](Week10-11.ipynb) | Câu 41 | `inv_bordering()` |
| Nghịch đảo bằng lặp Jacobi / Gauss-Seidel | 10–11 | [Week10-11.ipynb](Week10-11.ipynb) | Câu 42a | `inv_iterative()` |
| Nghịch đảo bằng lặp tựa Newton (Newton–Schulz) | 10–11 | [Week10-11.ipynb](Week10-11.ipynb) | Câu 42b, 42c | `inv_newton()` |

### A.5 Giá trị riêng & vector riêng

| Phương pháp | Tuần | File | Câu / Vị trí | Hàm chính |
|---|---|---|---|---|
| Danilevski (đa thức đặc trưng) | 12–13 | [Week12-13.ipynb](Week12-13.ipynb) | Câu 43 | `danilevski()` |
| Danilevski (giá trị & vector riêng) | 12–13 | [Week12-13.ipynb](Week12-13.ipynb) | Câu 44 | `eig_danilevski()`, `danilevski_full()` |
| Lũy thừa (Power Method) | 12–13 | [Week12-13.ipynb](Week12-13.ipynb) | Câu 45 | `power_method()` |
| Xuống thang (Deflation / Hotelling) | 12–13 | [Week12-13.ipynb](Week12-13.ipynb) | Câu 46 | `second_eigen()` |
| Tất cả GTR bằng Lũy thừa + Xuống thang | 12–13 | [Week12-13.ipynb](Week12-13.ipynb) | Câu 47 | `all_eigen_deflation()` |

### A.6 Giá trị kỳ dị (SVD) & số điều kiện

| Phương pháp | Tuần | File | Câu / Vị trí | Hàm chính |
|---|---|---|---|---|
| σ lớn nhất (Power Method trên AᵀA) | 14–15 | [Week14-15.ipynb](Week14-15.ipynb) | Câu 48, 51, 52 | `largest_singular()` |
| SVD bằng Lũy thừa + Xuống thang | 14–15 | [Week14-15.ipynb](Week14-15.ipynb) | Câu 49 | `svd_deflation()` |
| Số điều kiện κ₂(A) | 14–15 | [Week14-15.ipynb](Week14-15.ipynb) | Câu 50 | `cond_number()` |
| Xấp xỉ hạng thấp (low-rank / nén ảnh) | 14–15 | [Week14-15.ipynb](Week14-15.ipynb) | Câu 51, 52 | `low_rank_approx()` |

### A.7 Lý thuyết sai số (không có code thuật toán)

| Chủ đề | Tuần | File | Vị trí |
|---|---|---|---|
| Số gần đúng, chữ số đáng tin, quy tắc làm tròn | 1 | [Week1.ipynb](Week1.ipynb) | cell 0, mục 1–4 |
| Lan truyền sai số & ảnh hưởng đều | 1 | [Week1.ipynb](Week1.ipynb) | cell 0, mục 5–6 + Bài tập 1–6 |

---

## B. Chi tiết theo tuần

### Week 1 — Sai số và số gần đúng · [Week1.ipynb](Week1.ipynb)
*Lý thuyết nền tảng, chưa có thuật toán số.*
- Số gần đúng và sai số; Chữ số đáng tin; Quy tắc làm tròn (cell 0, mục 1–3)
- Sai số của phép tính số học (mục 4)
- Nguyên lý lan truyền sai số — ví dụ thể tích cầu $V=\pi d^3/6$ (mục 5)
- Nguyên lý ảnh hưởng đều của sai số (mục 6)
- Bài tập 1–6 (dạng thi)

### Week 2 — Phương pháp Chia Đôi · [Week2.ipynb](Week2.ipynb)
- `tinh_pi()` — tính π (cell 3)
- `tinh_can()` — tính căn (cell 5)
- **Bisection** — `bisection()` (cell 8, 11, 14)
- Lý thuyết tổng quát "Phương pháp Chia Đôi" (cell 12): sai số tiên nghiệm (3a) & hậu nghiệm (3b), so sánh tiêu chuẩn dừng, ưu/nhược điểm

### Week 3 — Dây cung & Tiếp tuyến Newton · [Week3.ipynb](Week3.ipynb)
- **Câu 7** (cell 1–5): thuật toán dây cung (sai số mục tiêu / 2 lần xấp xỉ liên tiếp); thuật toán tiếp tuyến Newton (2 cách sai số)
- **Câu 8** (cell 6–13): tính số $e$ và $\pi$ — `bisect_chord()`, `newton()`, `day_cung()`
- **Câu 9** (cell 14–16): tính $\sqrt[n]{a}$ — `tinh_can()`, `day_cung()`, `newton()`
- **Câu 10** (cell 17–20): `day_cung()`, `newton()`
- **Câu 11** (cell 21–25): $x^5-3x^3+2x^2-x+5=0$ — `day_cung()`, `newton()`

### Week 4 — Lặp đơn (vô hướng) · [Week4.ipynb](Week4.ipynb)
- **Câu 12** (cell 1–2): thuật toán **lặp đơn**, điều kiện Định lý 2.1, sai số tiên/hậu nghiệm, công thức dừng, sơ đồ khối
- **Câu 13** (cell 3–9): `phi()`, `lap_don()` (3 bộ áp dụng)
- **Câu 14** (cell 11)

### Week 5 — Hệ phi tuyến: Lặp đơn & Newton · [Week5.ipynb](Week5.ipynb)
- **Câu 15** (cell 0–4): **lặp đơn giải hệ phi tuyến** — `lap_don()`, `phi()`, `phi3()`; điều kiện hội tụ, ước lượng số bước tiên nghiệm
- **Câu 16** (cell 5–9): **Newton giải hệ phi tuyến** — ma trận Jacobi, `newton_N()` (dừng sau N bước), `newton_eps()` (dừng theo ε); áp dụng hệ 2D `F()/J()` và 3D `F3()/J3()`

### Week 6 — Gauss & Gauss-Jordan · [Week6.ipynb](Week6.ipynb)
- **Câu 23** (cell 0–1): Quy trình thuận — **khử Gauss**
- **Câu 24** (cell 2): Quy trình ngược — **thế ngược**, các trường hợp nghiệm
- **Câu 25** (cell 3–4): `gauss_solve()`, `print_matrix()`
- Lý thuyết tổng hợp (cell 5): Gauss cơ bản → Gauss có **chọn phần tử chủ** (partial pivoting) → **Gauss-Jordan**; so sánh 3 phương pháp — `gauss_jordan()` (cell 6)

### Week 7 — LU (Doolittle) & Cholesky · [Week7.ipynb](Week7.ipynb)
- **Câu 27** (cell 0–1): **phân tách LU Doolittle** — `lu_decompose()`; áp dụng ma trận cấp 6
- **Câu 28** (cell 2–4): **giải AX=B bằng LU** — `lu_solve()`, `forward_sub()`, `backward_sub()`; hệ cấp 7 (3 bước: LU → thế xuôi → thế ngược)
- **Câu 29** (cell 5–7): **phân tách Cholesky** — `cholesky_decompose()`; điều kiện đối xứng xác định dương; ma trận cấp 8
- **Câu 30** (cell 8–10): **giải AX=B bằng Cholesky** $A=LL^T$ — `cholesky_solve()`; hệ cấp 7

### Week 8 — Hệ tuyến tính: Lặp đơn & Jacobi · [Week8.ipynb](Week8.ipynb)
- **Câu 31** (cell 0–2): **lặp đơn** — `lap_don()`; điều kiện hội tụ
- **Câu 32** (cell 3–5): **lặp Jacobi** — `jacobi()`
- **Câu 33** (cell 6–7): dùng lại LU — `lu_solve()`
- **Câu 34** (cell 8–10): `lap_don()` + `lu_solve()`
- **Câu 35** (cell 11)
- **Câu 36** (cell 12–13): tổng hợp
- **Câu 36a** (cell 14–15): lặp đơn cho $x=Bx+g$ — `lap_don()`
- **Câu 36b** (cell 16–18): Jacobi cho $Ax=b$ đưa về $x=Bx+g$ — `jacobi()`

### Week 9 — Gauss-Seidel & Seidel · [Week9.ipynb](Week9.ipynb)
- **Câu 37** (cell 0–1): **lặp Gauss-Seidel** — điều kiện hội tụ
- **Câu 38** (cell 2–3): `gauss_seidel()`
- **Câu 39** (cell 4–5): **lặp Seidel** dạng $x=Bx+d$ — `seidel()`

### Week 10–11 — Ma trận nghịch đảo · [Week10-11.ipynb](Week10-11.ipynb)
- **Câu 39** (cell 0–2): nghịch đảo bằng **Gauss-Jordan** — `inv_gauss_jordan()`
- **Câu 40** (cell 3–5): nghịch đảo bằng **Cholesky** — `inv_cholesky()`, `cholesky()`, `forward_sub()`, `back_sub_T()`
- **Câu 41** (cell 6–8): nghịch đảo bằng **viền quanh (bordering)** — `inv_bordering()`
- **Câu 42a** (cell 9–11): nghịch đảo bằng **lặp Jacobi / Gauss-Seidel** — `inv_iterative()`, `solve_jacobi()`, `solve_gauss_seidel()`
- **Câu 42b** (cell 12–14): nghịch đảo bằng **lặp tựa Newton (Newton–Schulz)** — `inv_newton()`
- **Câu 42c** (cell 15–17): chọn phương pháp & chạy ma trận cấp 8 ($a=200$) — `inv_newton()` (dừng theo ε)

### Week 12–13 — Giá trị riêng & vector riêng · [Week12-13.ipynb](Week12-13.ipynb)
- **Câu 43** (cell 0–2): **Danilevski** — đa thức đặc trưng — `danilevski()`, `_poly_str()`
- **Câu 44** (cell 3–5): giá trị & vector riêng bằng Danilevski — `eig_danilevski()`, `danilevski_full()`
- **Câu 45** (cell 6–8): **phương pháp Lũy thừa (Power Method)** — `power_method()`
- **Câu 46** (cell 9–11): **xuống thang (Deflation / Hotelling)** cho ma trận đối xứng — `second_eigen()`
- **Câu 47** (cell 12–14): tất cả GTR bằng Lũy thừa + Xuống thang — `all_eigen_deflation()`

### Week 14–15 — SVD & số điều kiện · [Week14-15.ipynb](Week14-15.ipynb)
- **Câu 48** (cell 0–2): **σ lớn nhất** — Power Method trên $A^TA$ — `largest_singular()`
- **Câu 49** (cell 3–5): **khai triển SVD** bằng Lũy thừa + Xuống thang — `svd_deflation()`
- **Câu 50** (cell 6–8): **số điều kiện** $\kappa_2(A)$ — `cond_number()`
- **Câu 51** (cell 9–11): σ lớn nhất + vector kỳ dị trái/phải; ý tưởng xuống thang; **xấp xỉ hạng thấp** ($\|A-B\|_F/\|A\|_F \le 5\%$); SVD nén ảnh — `low_rank_approx()`
- **Câu 52** (cell 12–14): σ lớn nhất; 3 giá trị kỳ dị lớn nhất & **xấp xỉ hạng-3** — `svd_deflation()`, `largest_singular()`

---

*Hàm tiện ích lặp lại nhiều notebook: `_sci()` (in số dạng khoa học), `_print_mat()`, `_print_vec()`, `_fmt()`, `forward_sub()`, `backward_sub()`.*
