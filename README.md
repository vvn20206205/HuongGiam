<!-- Tìm chính xác theo tia -->
1. Với x_k, d_k, f đã cho (gradient f(x_k) khác 0)
2. Đặt phi_k(t) = f(x_k+t*d_k)
3. Tìm t_k = argmin phi_k(t)
* Có thể giải t_k bằng hệ
====phi_k(t_k) đạo hàm cấp 1 = 0
====Và phi_k(t_k) đạo hàm cấp 2 > 0
* Nếu  f là hàm toàn phương lồi chặt tk= - [(A*x_k-b)T*d_k] / [(d_k)T*A*d_k] >0
<!-- Thủ tục quay lui -->
1. Với x_k, d_k, f đã cho (gradient f(x_k) khác 0)
2. Chọn 0 <m1 < 1, 0 < alpha < 1
3. Đặt t_k=1
4. Tính x_k+1=x_k+t_k*d_k
5. IF f(x_k+1)=<f(x_k)+m1*t_k*<gradient f(x_k),d_k>:
5.1. Dừng vòng lặp ta có x_k+1
5.2. ELSE: t_k=alpha*t_k
<!-- PP gradient -->
Chung d_k= -gradient f(x_k)
<!-- PP gradient theo tia -->
1. Khởi đầu: e>0, x0 tùy ý, k=0 (gradient f(x_k) khác 0)
2. Vòng lặp:
2.1. Đặt phi_k(t) = f(x_k-t*gradient f(x_k))
2.2. Tìm t_k = argmin phi_k(t)
* Có thể giải t_k bằng hệ
====phi_k(t_k) đạo hàm cấp 1 = 0
====Và phi_k(t_k) đạo hàm cấp 2 > 0
2.3. Tính x_k+1 = x_k-t_k*gradient f(x_k)
2.4. IF CHUẨN ||f(x_k+1)||<e 
2.4.1. Dừng vòng lặp ta có x*:=x_k+1
2.4.2. ELSE: k:=k+1 quay lại bước lặp 2 
* Nếu  f là hàm toàn phương lồi chặt tk= - [(A*x_k-b)T*gradient f(x_k)] / [(gradient f(x_k))T*A*gradient f(x_k)] >0
<!-- PP gradient thủ tục quay lui  -->
1. Khởi đầu: 0 <m1 < 1, 0 < alpha < 1, e>0, x0 tùy ý, k=0 (gradient f(x_k) khác 0)
2. Vòng lặp:
2.1. Đặt t_k=1
2.2. Tính x_k+1=x_k-t_k*gradient f(x_k)
2.3. IF f(x_k+1)-f(x_k)=<-m1*t_k*||gradient f(x_k)||^2:
2.3.1. Dừng vòng lặp chuyển sang bước xxx
2.3.2. ELSE: t_k=alpha*t_k
2.4. IF CHUẨN ||f(x_k+1)||<e
2.4.1. Dừng vòng lặp ta có x*:=x_k+1
2.4.2. ELSE: k:=k+1 quay lại bước lặp 2
<!-- PP Newton thuần túy -->
1. Khởi đầu:  e>0, x0 đủ gần x*, k=0 (gradient f(x_k) khác 0)
2. Vòng lặp:
2.1. Tính p_k = -[hesen f(x_k)]^-1 * [gradient f(x_k)]
2.2. Tính x_k+1=x_k+p_k
2.3. IF CHUẨN ||f(x_k+1)||<e 
2.3.1. Dừng vòng lặp ta có x*:=x_k+1
2.3.2. ELSE: k:=k+1 quay lại bước lặp 2 
<!-- PP Newton hiệu chỉnh -->
1.1. Khởi đầu: e>0, x0 tùy ý, k=0 (gradient f(x_k) khác 0)
1.2. Chọn 0 <m1 < 1, 0 < alpha < 1
2. Vòng lặp:
2.1. Tính d_k = -[hesen f(x_k)]^-1 * [gradient f(x_k)]
2.2. Đặt t_k=1
2.3. Tính x_k+1=x_k+t_k*d_k
2.4. IF f(x_k+1)=<f(x_k)+m1*t_k*<gradient f(x_k),d_k>:
2.4.1. Dừng vòng lặp ta có x_k+1
2.4.2. ELSE: t_k=alpha*t_k
2.5. Vậy  x_k+1=x_k+t_k*d_k
2.6. IF CHUẨN ||f(x_k+1)||<e 
2.6.1. Dừng vòng lặp ta có x*:=x_k+1
2.6.2. ELSE: k:=k+1 quay lại bước lặp 2 
