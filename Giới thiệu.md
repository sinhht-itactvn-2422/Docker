Docker là một nền tảng mã nguồn mở tự động hóa việc triển khai, mở rộng và quản lý các ứng dụng bằng cách cô lập chúng vào các containers nhẹ và di động. Containers là các đơn vị thực thi độc lập, đóng gói tất cả các phụ thuộc cần thiết, thư viện và các tệp cấu hình cần thiết để một ứng dụng có thể chạy nhất quán trên các môi trường khác nhau.

## 1. Container là gì?

Containers là các môi trường phần mềm nhẹ, di động và cô lập, cho phép các nhà phát triển chạy và đóng gói ứng dụng cùng với các phụ thuộc của chúng, một cách nhất quán trên các nền tảng khác nhau. Chúng giúp đơn giản hóa quá trình phát triển, triển khai và quản lý ứng dụng, đồng thời đảm bảo rằng ứng dụng chạy nhất quán, bất kể cơ sở hạ tầng nền tảng là gì.

### 1.1 Container hoạt động như thế nào?

Không giống như ảo hóa truyền thống, mô phỏng một hệ điều hành hoàn chỉnh với các tài nguyên phần cứng của nó, containers chia sẻ kernel của hệ điều hành chủ và tận dụng các kỹ thuật ảo hóa nhẹ để tạo ra các quy trình cô lập. Cách tiếp cận này mang lại một số lợi ích, bao gồm:

* ***Hiệu quả***: Containers có ít chi phí hơn và có thể chia sẻ các thư viện và tệp thực thi chung, làm cho việc chạy nhiều containers trên một máy chủ đơn trở nên khả thi hơn so với các máy ảo (VM).
* ***Di động***: Containers đóng gói ứng dụng và các phụ thuộc của chúng, do đó chúng có thể dễ dàng di chuyển và chạy nhất quán trên các môi trường và nền tảng khác nhau.
Khởi động nhanh: Vì containers không cần khởi động một hệ điều hành đầy đủ, chúng có thể khởi động và tắt nhanh hơn nhiều so với VM.
* ***Nhất quán***: Containers cung cấp một môi trường nhất quán cho các giai đoạn phát triển, thử nghiệm và sản xuất của ứng dụng, giảm thiểu vấn đề “nó chạy trên máy của tôi”.

![image](https://www.docker.com/wp-content/uploads/2021/11/docker-containerized-and-vm-transparent-bg.png)

## 1.2 Containers và Docker

Docker là một nền tảng đơn giản hóa quá trình tạo, triển khai và quản lý containers. Nó cung cấp cho các nhà phát triển và quản trị viên một bộ công cụ và API để quản lý các ứng dụng containerized. Với Docker, bạn có thể xây dựng và đóng gói mã ứng dụng, thư viện và các phụ thuộc vào một container image, có thể phân phối và chạy nhất quán trong bất kỳ môi trường nào hỗ trợ Docker.

## 2. Nhu cầu về Container

Trong thế giới phát triển và triển khai phần mềm, tính nhất quán và hiệu quả là vô cùng quan trọng. Trước khi containers ra đời, các nhà phát triển thường gặp phải những thách thức khi triển khai ứng dụng trên các môi trường khác nhau, bao gồm:

* ***Môi trường không nhất quán***: Các nhà phát triển thường làm việc trong các môi trường khác nhau có thể có các cấu hình và thư viện khác so với các máy chủ sản xuất. Điều này dẫn đến các vấn đề tương thích khi triển khai ứng dụng.
* ***Sử dụng tài nguyên không hiệu quả***: Máy ảo (VM) được sử dụng rộng rãi để khắc phục sự không nhất quán môi trường. Tuy nhiên, VM yêu cầu phải chạy một hệ điều hành hoàn chỉnh cho mỗi ứng dụng, làm cho việc sử dụng tài nguyên trở nên không hiệu quả.
* ***Quá trình chậm chạp và vấn đề mở rộng***: Các phương pháp triển khai truyền thống có thời gian đưa ra thị trường chậm hơn và gặp khó khăn trong việc mở rộng, điều này cản trở việc cung cấp các bản cập nhật phần mềm nhanh chóng.

**Containers giải quyết những thách thức này như thế nào?**

* ***Môi trường nhất quán***: Containers giải quyết sự không nhất quán môi trường bằng cách đóng gói một ứng dụng và các phụ thuộc, cấu hình và thư viện của nó vào một container duy nhất. Điều này đảm bảo rằng ứng dụng chạy mượt mà trên các môi trường khác nhau.
* ***Sử dụng tài nguyên hiệu quả***: Không giống như VM, containers chia sẻ tài nguyên hệ thống cơ bản và kernel của hệ điều hành, làm cho chúng nhẹ và hiệu quả. Containers được thiết kế để sử dụng ít tài nguyên hơn và khởi động nhanh hơn, cải thiện việc sử dụng tài nguyên.
* ***Quá trình nhanh hơn và khả năng mở rộng***: Containers có thể dễ dàng được tạo, hủy và thay thế, dẫn đến các chu kỳ phát triển và triển khai nhanh hơn. Việc mở rộng ứng dụng trở nên dễ dàng hơn khi nhiều containers có thể được triển khai mà không tiêu tốn nhiều tài nguyên.

Nhìn chung, containers đã trở thành một công cụ thiết yếu cho các tổ chức muốn phản ứng nhanh chóng với các thay đổi của thị trường, cải thiện hiệu quả sử dụng tài nguyên và đảm bảo cung cấp phần mềm đáng tin cậy và nhất quán. Chúng đã cách mạng hóa các thực tiễn phát triển phần mềm hiện đại và có tác động lâu dài trong thế giới triển khai và quản lý ứng dụng.

## 3. Bare Metal vs VM vs Containers

| **Thuật ngữ** | **Bare Metal** | **Máy Ảo (VMs)** | **Containers** |
|---------------|----------------|-----------------|----------------|
| **Mô tả**     | Bare metal là thuật ngữ dùng để mô tả một máy tính chạy trực tiếp trên phần cứng mà không có bất kỳ ảo hóa nào. Đây là cách chạy ứng dụng có hiệu suất cao nhất, nhưng cũng là cách ít linh hoạt nhất. Bạn chỉ có thể chạy một ứng dụng trên mỗi máy chủ và không thể dễ dàng di chuyển ứng dụng sang máy chủ khác. | Máy ảo (VM) là cách để chạy nhiều ứng dụng trên một máy chủ duy nhất. Mỗi VM chạy trên một hypervisor, là một phần mềm giả lập phần cứng của máy tính. Hypervisor cho phép bạn chạy nhiều hệ điều hành trên một máy chủ duy nhất, và cũng cung cấp sự cô lập giữa các ứng dụng chạy trên các VM khác nhau. | Containers là cách để chạy nhiều ứng dụng trên một máy chủ duy nhất mà không có chi phí của hypervisor. Mỗi container chạy trên một container engine, là một phần mềm giả lập hệ điều hành của máy tính. Container engine cho phép bạn chạy nhiều ứng dụng trên một máy chủ duy nhất và cũng cung cấp sự cô lập giữa các ứng dụng chạy trên các containers khác nhau. |

## 4. Docker và OCI

Open Container Initiative (OCI) là một dự án của Linux Foundation nhằm tạo ra các tiêu chuẩn công nghiệp cho các định dạng và runtime của container. Mục tiêu chính của nó là đảm bảo tính tương thích và khả năng tương tác của các môi trường container thông qua các thông số kỹ thuật được định nghĩa.

***Vai trò của Docker trong OCI***: Docker là một trong những thành viên sáng lập của OCI và đã đóng vai trò quan trọng trong việc định hình các tiêu chuẩn cho định dạng và runtime của container. Docker ban đầu đã phát triển runtime container (Docker Engine) và định dạng image (Docker Image), làm cơ sở cho các thông số kỹ thuật của OCI.

***Các thông số kỹ thuật của OCI***: OCI có ba thông số kỹ thuật chính:

* ***Runtime Specification (runtime-spec)***: Định nghĩa thông số kỹ thuật để thực thi một container thông qua một công nghệ cách ly, như container engine. Runtime container được Docker xây dựng, gọi là 'containerd', đã hướng dẫn phát triển runtime-spec của OCI.
* ***Image Specification (image-spec)***: Định nghĩa định dạng image của container, mô tả nội dung của một container và có thể được chạy bởi một runtime tương thích. Định dạng image ban đầu của Docker đã dẫn đến sự ra đời của image-spec của OCI.
* ***Distribution Specification (distribution-spec)***: Định nghĩa một giao thức API để tạo điều kiện và tiêu chuẩn hóa việc phân phối nội dung. API registry hiện có của Docker đã làm điểm khởi đầu và ảnh hưởng lớn đến thiết kế của Distro Spec của OCI.

***Tính tương thích giữa Docker và OCI***: Docker cam kết hỗ trợ các thông số kỹ thuật của OCI và kể từ khi tham gia OCI, đã liên tục cập nhật phần mềm của mình để tuân thủ các tiêu chuẩn của OCI. Runtime containerd và định dạng image của Docker hoàn toàn tương thích với các thông số kỹ thuật của OCI, cho phép các container của Docker được chạy bởi các runtime container tuân thủ OCI và ngược lại.

Docker và Open Container Initiative cùng nhau duy trì sự tiêu chuẩn hóa và tính tương thích trong ngành container. Docker đã đóng một vai trò quan trọng trong sự phát triển của các thông số kỹ thuật OCI, đảm bảo rằng hệ sinh thái container vẫn khỏe mạnh, tương tác tốt và dễ tiếp cận cho một loạt người dùng và nền tảng trong toàn ngành.
