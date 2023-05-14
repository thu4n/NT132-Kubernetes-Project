# NT132-Kubernetes-Project
Đây là repository để lưu trữ code cho ứng dụng web đơn giản, phục vụ cho mục dích demo các tính năng của Kubernetes. Mọi thay đổi sẽ được ánh xạ qua repository trên CSR để build và deploy.

Thành viên nhóm:
- Tống Võ Anh Thuận - 21522652 (trưởng nhóm)
- Nguyễn Lê Tiến Phát - 21522446
- Nguyễn Thị Yến Ly - 21522316
## Nội dung demo
Sử dụng Kubernetes để triển khai và vận hành một ứng dụng web trên một multi-node cluster và thể hiện một số tính năng chính của Kubernetes trên cluster được tạo. Xuyên suốt demo sẽ sử dụng các dịch vụ được cung cấp bởi Google Cloud Platform.
## Công nghệ sử dụng
-	**ASP.NET Core:** Framework sử dụng để tạo ứng dụng web. 
-	**Docker:** Đóng gói và tạo Docker image của ứng dụng web.
-	**Google Kubernetes Engine (GKE):** Dịch vụ Kubernetes được cung cấp bởi GCP. 
-	**Google Container Registry (GCR):** Dịch vụ lưu trữ Docker image 
-	**GitHub:** Lưu trữ code và kiểm soát phiên bản. Dành cho phía developer (nhà phát triển) sử dụng.
-	**Cloud Source Repositories (CSR):** Bản sao “read-only” của repository trên GitHub. Dành cho phía operator (người vận hành) sử dụng.

## Các bước thực hiện demo (luồng công việc)
1.	Developer viết code cho ứng dụng web của mình. Khi hoàn tất, tiến hành commit lên repository trên GitHub.
2.	Các đoạn code trên GitHub được ánh xạ qua repository trên CSR.
3.	Operator nhận được thông báo và xem qua đoạn code được cập nhật trên CSR.
4.	Operator tiến hành xây dựng Docker image từ repository và đẩy lên GCR.
5.	Triển khai ứng dụng web thông qua việc đặt container được tạo ra từ image trên GCR lên cluster của GKE (Tạo deployment).
6.	Thực hiện thêm các tác vụ như sau:
    -	Expose service với external IP để đi ra được Internet,
    -   Tạo các bản replica với số lượng mong muốn,
    - Thử xóa pod để kiểm tra tính chống chịu,
    - Cập nhật ứng dụng web trong thời gian thực (không có down-time),
    - Theo dõi Kubernetes Graphical dashboard,
    - Xem dữ liệu log của cluster.

