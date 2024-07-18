Linux Containers (LXC)
Linux Containers (LXC) cho phép chạy nhiều hệ thống Linux độc lập trên một máy tính duy nhất. Hoạt động như các không gian cách ly, containers LXC chia sẻ tài nguyên của máy chủ như bộ nhớ và sức mạnh xử lý, mà không cần một bản sao hệ điều hành đầy đủ, đảm bảo nhẹ và khởi động nhanh. Di động trên các hệ thống Linux tương thích, chúng được sử dụng trong các nhiệm vụ đa dạng như chạy các ứng dụng riêng biệt, thử nghiệm phần mềm hoặc triển khai các dịch vụ đám mây. Với các công cụ quản lý thân thiện với người dùng, LXC đơn giản hóa việc tạo, giám sát và quản lý containers.

Control Groups (cgroups)
Control Groups (cgroups) là một tính năng của kernel Linux cho phép phân bổ và quản lý các tài nguyên như CPU, bộ nhớ và I/O cho một tập hợp các tiến trình. Docker tận dụng cgroups để giới hạn tài nguyên sử dụng bởi các containers và đảm bảo rằng một container không chiếm dụng toàn bộ tài nguyên của hệ thống chủ.

Union File Systems (UnionFS)
UnionFS là một dịch vụ hệ thống tệp cho phép lớp phủ của nhiều hệ thống tệp trong một chế độ xem hợp nhất duy nhất. Docker sử dụng UnionFS để tạo ra một cách tiếp cận lớp cho các image và container, giúp chia sẻ tốt hơn các tệp chung và tạo container nhanh hơn.

Namespaces
Namespaces là một tính năng khác của kernel Linux cung cấp sự cách ly tiến trình. Chúng cho phép Docker tạo ra các không gian làm việc cách ly gọi là containers. Namespaces đảm bảo rằng các tiến trình trong một container không thể can thiệp vào các tiến trình ngoài container hoặc trên hệ thống chủ. Có một số loại namespaces, như PID, NET, MNT và USER, mỗi loại chịu trách nhiệm cách ly một khía cạnh khác nhau của tiến trình.
