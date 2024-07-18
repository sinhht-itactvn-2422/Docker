***Linux Containers (LXC)***: Linux Containers (LXC) cho phép chạy nhiều hệ thống Linux độc lập trên một máy tính duy nhất. Hoạt động như các không gian cách ly, containers LXC chia sẻ tài nguyên của máy chủ như bộ nhớ và sức mạnh xử lý, mà không cần một bản sao hệ điều hành đầy đủ, đảm bảo nhẹ và khởi động nhanh. Di động trên các hệ thống Linux tương thích, chúng được sử dụng trong các nhiệm vụ đa dạng như chạy các ứng dụng riêng biệt, thử nghiệm phần mềm hoặc triển khai các dịch vụ đám mây. Với các công cụ quản lý thân thiện với người dùng, LXC đơn giản hóa việc tạo, giám sát và quản lý containers.

## 1. Namespaces

Namespaces là một trong những công nghệ cốt lõi mà Docker sử dụng để cung cấp sự cô lập giữa các containers. 

***Namespaces là gì?***: Trong kernel Linux, namespaces là một tính năng cho phép cô lập các tài nguyên hệ thống khác nhau, làm cho một tiến trình và các tiến trình con của nó có thể có một cái nhìn về một phần của hệ thống tách biệt với các tiến trình khác. Namespaces giúp tạo ra một lớp trừu tượng để giữ cho các tiến trình được container hóa tách biệt nhau và khỏi hệ thống chủ.

Có một số loại namespaces trong Linux, bao gồm:

* ***PID (Process IDs)***: Cô lập không gian số ID tiến trình, nghĩa là các tiến trình trong một container chỉ nhìn thấy các tiến trình của chính nó, không phải của hệ thống chủ hoặc các container khác.
* ***Network (NET)***: Cung cấp cho mỗi container một cái nhìn riêng về ngăn xếp mạng, bao gồm các giao diện mạng, bảng định tuyến và các quy tắc tường lửa riêng.
* ***Mount (MNT)***: Cô lập các điểm gắn kết hệ thống tệp sao cho mỗi container có hệ thống tệp gốc riêng của nó, và các tài nguyên được gắn kết chỉ xuất hiện trong container đó.
* ***UTS (UNIX Time Sharing System)***: Cho phép mỗi container có hostname và domain name riêng, tách biệt với các container khác và hệ thống chủ.
* ***User (USER)***: Ánh xạ các định danh người dùng và nhóm giữa container và hệ thống chủ, do đó có thể thiết lập các quyền khác nhau cho các tài nguyên trong container.
* ***IPC (Inter-Process Communication)***: Cho phép hoặc hạn chế việc giao tiếp giữa các tiến trình trong các containers khác nhau.

***Cách Docker sử dụng Namespaces***: Docker sử dụng namespaces để tạo ra các môi trường cô lập cho containers. Khi một container được khởi động, Docker tạo ra một tập hợp namespaces mới cho container đó. Những namespaces này chỉ áp dụng trong container, vì vậy bất kỳ tiến trình nào chạy bên trong container đều có quyền truy cập vào một phần tài nguyên hệ thống được cô lập khỏi các container khác cũng như hệ thống chủ. Bằng cách tận dụng namespaces, Docker đảm bảo rằng containers thực sự di động và có thể chạy trên bất kỳ hệ thống nào mà không có xung đột hoặc can thiệp từ các tiến trình hoặc containers khác chạy trên cùng một hệ thống chủ.

Namespaces cung cấp một mức độ cô lập tài nguyên cho phép chạy nhiều containers với các tài nguyên hệ thống riêng biệt trong cùng một hệ thống chủ, mà không can thiệp lẫn nhau. Đây là một tính năng quan trọng tạo nền tảng cho công nghệ container của Docker.
