***Linux Containers (LXC)***: Linux Containers (LXC) cho phép chạy nhiều hệ thống Linux độc lập trên một máy tính duy nhất. Hoạt động như các không gian cách ly, containers LXC chia sẻ tài nguyên của máy chủ như bộ nhớ và sức mạnh xử lý, mà không cần một bản sao hệ điều hành đầy đủ, đảm bảo nhẹ và khởi động nhanh. Di động trên các hệ thống Linux tương thích, chúng được sử dụng trong các nhiệm vụ đa dạng như chạy các ứng dụng riêng biệt, thử nghiệm phần mềm hoặc triển khai các dịch vụ đám mây. Với các công cụ quản lý thân thiện với người dùng, LXC đơn giản hóa việc tạo, giám sát và quản lý containers.

## 1. Namespaces

Namespaces là một trong những công nghệ cốt lõi mà Docker sử dụng để cung cấp sự cô lập giữa các containers. 

***Namespaces là gì?***: Trong kernel Linux, namespaces là một tính năng cho phép cô lập các tài nguyên hệ thống khác nhau, làm cho một tiến trình và các tiến trình con của nó có thể có một cái nhìn về một phần của hệ thống tách biệt với các tiến trình khác. Namespaces giúp tạo ra một lớp trừu tượng để giữ cho các tiến trình được container hóa tách biệt nhau và khỏi hệ thống chủ.

**Có một số loại namespaces trong Linux, bao gồm**:

* ***PID (Process IDs)***: Cô lập không gian số ID tiến trình, nghĩa là các tiến trình trong một container chỉ nhìn thấy các tiến trình của chính nó, không phải của hệ thống chủ hoặc các container khác.
* ***Network (NET)***: Cung cấp cho mỗi container một cái nhìn riêng về ngăn xếp mạng, bao gồm các giao diện mạng, bảng định tuyến và các quy tắc tường lửa riêng.
* ***Mount (MNT)***: Cô lập các điểm gắn kết hệ thống tệp sao cho mỗi container có hệ thống tệp gốc riêng của nó, và các tài nguyên được gắn kết chỉ xuất hiện trong container đó.
* ***UTS (UNIX Time Sharing System)***: Cho phép mỗi container có hostname và domain name riêng, tách biệt với các container khác và hệ thống chủ.
* ***User (USER)***: Ánh xạ các định danh người dùng và nhóm giữa container và hệ thống chủ, do đó có thể thiết lập các quyền khác nhau cho các tài nguyên trong container.
* ***IPC (Inter-Process Communication)***: Cho phép hoặc hạn chế việc giao tiếp giữa các tiến trình trong các containers khác nhau.

***Cách Docker sử dụng Namespaces***: Docker sử dụng namespaces để tạo ra các môi trường cô lập cho containers. Khi một container được khởi động, Docker tạo ra một tập hợp namespaces mới cho container đó. Những namespaces này chỉ áp dụng trong container, vì vậy bất kỳ tiến trình nào chạy bên trong container đều có quyền truy cập vào một phần tài nguyên hệ thống được cô lập khỏi các container khác cũng như hệ thống chủ. Bằng cách tận dụng namespaces, Docker đảm bảo rằng containers thực sự di động và có thể chạy trên bất kỳ hệ thống nào mà không có xung đột hoặc can thiệp từ các tiến trình hoặc containers khác chạy trên cùng một hệ thống chủ.

Namespaces cung cấp một mức độ cô lập tài nguyên cho phép chạy nhiều containers với các tài nguyên hệ thống riêng biệt trong cùng một hệ thống chủ, mà không can thiệp lẫn nhau. Đây là một tính năng quan trọng tạo nền tảng cho công nghệ container của Docker.

## 2. cgroups

cgroups, hay control groups, là một tính năng của kernel Linux cho phép bạn phân bổ và quản lý các tài nguyên như CPU, bộ nhớ, băng thông mạng và I/O giữa các nhóm tiến trình đang chạy trên hệ thống. Nó đóng vai trò quan trọng trong việc cung cấp sự cô lập tài nguyên và giới hạn các tài nguyên mà một container đang chạy có thể sử dụng.

Docker sử dụng cgroups để thực thi các giới hạn tài nguyên trên containers, cho phép chúng có hành vi nhất quán và dự đoán được. Dưới đây là một số tính năng và lợi ích chính của cgroups trong bối cảnh containers của Docker:

* ***Cô lập tài nguyên***: cgroups giúp giới hạn mỗi container vào một tập hợp tài nguyên cụ thể, đảm bảo chia sẻ công bằng các tài nguyên hệ thống giữa nhiều containers. Điều này cho phép cô lập tốt hơn giữa các containers khác nhau, sao cho một container hoạt động không đúng không thể tiêu thụ tất cả tài nguyên sẵn có, từ đó ảnh hưởng tiêu cực đến các containers khác.

* ***Giới hạn tài nguyên***: Với cgroups, bạn có thể đặt giới hạn trên các tài nguyên hệ thống khác nhau mà một container sử dụng, chẳng hạn như CPU, bộ nhớ và I/O. Điều này giúp ngăn chặn một container duy nhất tiêu thụ quá nhiều tài nguyên và gây ra các vấn đề hiệu suất cho các containers khác hoặc hệ thống chủ.

* ***Ưu tiên containers***: Bằng cách phân bổ các phần tài nguyên khác nhau, cgroups cho phép bạn ưu tiên cho các containers nhất định. Điều này có thể hữu ích trong các tình huống mà một số containers quan trọng hơn các containers khác hoặc trong các tình huống tranh chấp tài nguyên cao.

* ***Giám sát***: cgroups cũng cung cấp các cơ chế để giám sát việc sử dụng tài nguyên của các containers riêng lẻ, giúp nắm bắt thông tin về hiệu suất của container và xác định các nút thắt tài nguyên tiềm ẩn.

cgroups là một công nghệ nền tảng thiết yếu trong Docker. Bằng cách tận dụng cgroups, Docker cung cấp một môi trường runtime container mạnh mẽ và hiệu quả, đảm bảo các containers có tài nguyên cần thiết trong khi duy trì hiệu suất hệ thống tốt tổng thể.

## 3. Union Filesystems

Union filesystems, hay còn gọi là UnionFS, đóng vai trò quan trọng trong hoạt động tổng thể của Docker. Đây là một loại hệ thống tệp đặc biệt tạo ra một cấu trúc tệp phân lớp ảo bằng cách overlay (chồng) nhiều thư mục lên nhau. Thay vì thay đổi hệ thống tệp gốc hoặc hợp nhất các thư mục, UnionFS cho phép gắn kết đồng thời nhiều thư mục vào một điểm mount duy nhất trong khi giữ nội dung của chúng riêng biệt. Tính năng này đặc biệt có lợi trong bối cảnh Docker, vì nó cho phép quản lý và tối ưu hóa hiệu suất lưu trữ bằng cách giảm thiểu sự trùng lặp và giảm kích thước image của container.

**Một số tính năng chính của union filesystems:**

- ***Cấu trúc phân lớp:*** UnionFS xây dựng một cấu trúc phân lớp gồm nhiều lớp chỉ đọc và một lớp có thể ghi trên cùng. Cấu trúc này cho phép xử lý hiệu quả các thay đổi bằng cách chỉ cập nhật lớp có thể ghi, trong khi các lớp chỉ đọc bảo tồn dữ liệu gốc.
  
- ***Copy-on-Write (COW):*** Cơ chế copy-on-write là một tính năng không thể thiếu của UnionFS. Nếu một container thay đổi một tệp hiện có, hệ thống sẽ tạo ra một bản sao của tệp trong lớp có thể ghi, để nguyên tệp gốc trong lớp chỉ đọc. Quá trình này giới hạn việc sửa đổi ở lớp trên cùng, đảm bảo hoạt động nhanh và hiệu quả về tài nguyên.

- ***Chia sẻ tài nguyên:*** Union filesystems cho phép nhiều container chia sẻ các lớp cơ bản chung trong khi vẫn hoạt động riêng biệt. Tính năng này ngăn ngừa sự trùng lặp tài nguyên và tiết kiệm không gian lưu trữ đáng kể.

- ***Khởi tạo container nhanh:*** Union filesystems giúp tạo ra các container mới ngay lập tức bằng cách chỉ tạo ra một lớp có thể ghi mới trên các lớp chỉ đọc hiện có. Việc khởi tạo nhanh này giảm bớt khối lượng công việc trùng lặp các thao tác tệp, cuối cùng cải thiện hiệu suất.

**Các union filesystems phổ biến trong Docker:**

- ***AUFS (Advanced Multi-Layered Unification Filesystem):*** AUFS được sử dụng rộng rãi như một driver lưu trữ của Docker, cho phép quản lý hiệu quả các lớp phân tầng.

- ***OverlayFS (Overlay Filesystem):*** OverlayFS là một union filesystem khác được Docker hỗ trợ. Nó sử dụng một cách tiếp cận đơn giản hơn so với AUFS để tạo và quản lý các thư mục overlay.

- ***Btrfs (B-Tree Filesystem):*** Btrfs, một hệ thống tệp hiện đại, cung cấp khả năng tương thích với union filesystems cùng với các tính năng lưu trữ nâng cao như snapshot và checksumming.

- ***ZFS (Z File System):*** ZFS là một nền tảng lưu trữ có dung lượng cao và mạnh mẽ cung cấp các tính năng của union filesystem cùng với bảo vệ dữ liệu, nén và khử trùng lặp.
