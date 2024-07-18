## 1. Docker Desktop

Docker Desktop là một ứng dụng dễ cài đặt giúp các nhà phát triển nhanh chóng thiết lập môi trường Docker trên máy tính để bàn của họ. Nó có sẵn cho cả hệ điều hành Windows và macOS. Docker Desktop được thiết kế để đơn giản hóa quá trình quản lý và chạy containers Docker, cung cấp giao diện thân thiện với người dùng và tích hợp liền mạch với hệ điều hành máy chủ.

### 1.1 Các tính năng

**Dễ dàng cài đặt:** Docker Desktop cung cấp quy trình cài đặt đơn giản, cho phép người dùng nhanh chóng thiết lập Docker trên máy tính của họ.

**Cập nhật tự động:** Ứng dụng sẽ tự động cập nhật lên phiên bản mới nhất của Docker, đảm bảo môi trường của bạn luôn được cập nhật và bảo mật.

**Tích hợp Docker Hub:** Giao diện Docker Desktop cho phép dễ dàng truy cập Docker Hub, cho phép người dùng tìm, chia sẻ và quản lý các image Docker.

**Quản lý containers và services:** Docker Desktop đơn giản hóa việc quản lý container và services với giao diện GUI thân thiện, cho phép người dùng giám sát, khởi động, dừng và xóa containers và services.

**Tích hợp Kubernetes:** Docker Desktop đi kèm với hỗ trợ Kubernetes tích hợp, có thể được kích hoạt chỉ bằng một cú nhấp chuột. Điều này làm cho việc phát triển, kiểm tra và chạy các ứng dụng Kubernetes cục bộ trở nên dễ dàng hơn.

**Phân bổ tài nguyên:** Docker Desktop cho phép người dùng cấu hình lượng tài nguyên (CPU, bộ nhớ và lưu trữ) được phân bổ cho containers và services.

### 1.2 Cài đặt

**Tải xuống trình cài đặt:** Bạn có thể tải xuống trình cài đặt cho hệ điều hành của mình từ trang web [Docker Desktop](https://www.docker.com/products/docker-desktop). Đảm bảo chọn phiên bản phù hợp (Windows hoặc Mac).

**Chạy trình cài đặt:** Nhấp đúp vào tệp trình cài đặt đã tải xuống và làm theo trình hướng dẫn cài đặt để hoàn tất quá trình cài đặt.

**Khởi động Docker Desktop:** Sau khi cài đặt hoàn tất, khởi động Docker Desktop và đăng nhập bằng tài khoản Docker Hub của bạn. Nếu bạn chưa có tài khoản, bạn có thể đăng ký tài khoản miễn phí trên trang web [Docker Hub](https://hub.docker.com/).

**Xác minh cài đặt:** Mở terminal hoặc command prompt và chạy lệnh sau để xác minh rằng Docker Desktop đã được cài đặt đúng cách:

   ```sh
   docker --version
   ```

Nếu quá trình cài đặt thành công, lệnh sẽ xuất ra thông tin phiên bản Docker.
