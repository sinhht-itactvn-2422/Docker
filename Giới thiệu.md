## 1. Container là gì?

Containers là các môi trường phần mềm nhẹ, di động và cô lập, cho phép các nhà phát triển chạy và đóng gói ứng dụng cùng với các phụ thuộc của chúng, một cách nhất quán trên các nền tảng khác nhau. Chúng giúp đơn giản hóa quá trình phát triển, triển khai và quản lý ứng dụng, đồng thời đảm bảo rằng ứng dụng chạy nhất quán, bất kể cơ sở hạ tầng nền tảng là gì.

### 1.1 Container hoạt động như thế nào?

Không giống như ảo hóa truyền thống, mô phỏng một hệ điều hành hoàn chỉnh với các tài nguyên phần cứng của nó, containers chia sẻ kernel của hệ điều hành chủ và tận dụng các kỹ thuật ảo hóa nhẹ để tạo ra các quy trình cô lập. Cách tiếp cận này mang lại một số lợi ích, bao gồm:

* ***Hiệu quả***: Containers có ít chi phí hơn và có thể chia sẻ các thư viện và tệp thực thi chung, làm cho việc chạy nhiều containers trên một máy chủ đơn trở nên khả thi hơn so với các máy ảo (VM).
* ***Di động***: Containers đóng gói ứng dụng và các phụ thuộc của chúng, do đó chúng có thể dễ dàng di chuyển và chạy nhất quán trên các môi trường và nền tảng khác nhau.
Khởi động nhanh: Vì containers không cần khởi động một hệ điều hành đầy đủ, chúng có thể khởi động và tắt nhanh hơn nhiều so với VM.
* ***Nhất quán***: Containers cung cấp một môi trường nhất quán cho các giai đoạn phát triển, thử nghiệm và sản xuất của ứng dụng, giảm thiểu vấn đề “nó chạy trên máy của tôi”.
* 
![image](https://www.docker.com/wp-content/uploads/2021/11/docker-containerized-and-vm-transparent-bg.png)

## 1.2 Containers và Docker

Docker là một nền tảng đơn giản hóa quá trình tạo, triển khai và quản lý containers. Nó cung cấp cho các nhà phát triển và quản trị viên một bộ công cụ và API để quản lý các ứng dụng containerized. Với Docker, bạn có thể xây dựng và đóng gói mã ứng dụng, thư viện và các phụ thuộc vào một container image, có thể phân phối và chạy nhất quán trong bất kỳ môi trường nào hỗ trợ Docker.
