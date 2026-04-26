# Git and GitHub Fundamentals

## Overview of git and github
- Git is also known as Version Control System - VCS:
  - Tracks changes to source code
  - Recovers older versions
  - Facilitates collaboration
- Free and open-source software
- Distributed aspect makes it popular VCS
- Version control có thể control code, images, documents, other the types.

## Git
Bản thân nó có hỗ trợ tổ chức và quản lý feature branching qua command line interface (CLI)
Có các bên thứ 3 vai trò để lưu trữ repository như: Github, GitLab, Bitbucket, Beanstalk

**Github:** popular web-hosted services for Git repositories. 

**GitLab is:**
- A DevOps platform, delivered as a single application.
- Provides access to git repo
- Provides source code management

**-> enables developers to:**
- Collaborate
- Work from a local copy
- Branch a merge code
- Streamline testing and delivery with CI/CD

## Basic terms:
- **SSH protocol:** method to secure remote login
- **Repository:** Contains projects folders
- **Fork:** Copy of a repository
- **Pull request:** To request for review and approval
- **Working directory:** Contains files and subdirectories.
- **Commit:** snapshot of the project's current state
- **Branch:** Separate line of development
- **Merge:** Combines changes from one branch to another
- **Clone:** Local copy of the remote Git Repository

## Git

### 1. Lịch sử ra đời (Background & History)
**Bối cảnh (Context):** Cộng đồng Linux từng dùng BitKeeper (free-to-use). Năm 2005, BitKeeper chuyển sang thu phí (for-fee system).

**Kết quả (Result):** Linus Torvalds tạo ra Git để thay thế.

**Mục tiêu (Goals):** Xử lý dự án khổng lồ (large projects), tốc độ cao (high performance) và bảo mật (security/cryptographic authentication).

### 2. Sự khác biệt mô hình (Distributed vs. Centralized)

**Centralized Version Control (Hệ thống tập trung - Cũ):**
- Phụ thuộc vào Central Server (Máy chủ trung tâm).
- Mọi người phải Check-out và Commit trực tiếp lên đó. Nếu server sập, mọi việc bị đình trệ.

**Distributed Version Control (Hệ thống phân tán - Git):**
- Mỗi người có một Local Copy (Bản sao tại máy) chứa toàn bộ Full development history (Lịch sử phát triển đầy đủ).
- Hỗ trợ làm việc Offline.
- Mỗi máy cá nhân có thể đóng vai trò như một cái Hub để trao đổi code.

### 3. Đặc tính kỹ thuật cốt lõi (Core Characteristics)
- **Non-linear development (Phát triển phi tuyến tính):** Hỗ trợ hàng ngàn nhánh (Branches) chạy song song.
- **Cryptographic authentication (Xác thực bằng mật mã):** Đảm bảo tính toàn vẹn của dữ liệu (History integrity), không thể bị sửa đổi lén lút.
- **Pluggable merge strategies (Chiến lược gộp linh hoạt):** Có nhiều thuật toán để Merge (gộp code) từ các nhánh khác nhau một cách thông minh.

====================================

## What are branches
<img width="913" height="205" alt="image" src="https://github.com/user-attachments/assets/38a39a01-0c55-4b2c-a3b0-ea723eb02f52" />

Main branch stores the deployable code
<img width="906" height="271" alt="image" src="https://github.com/user-attachments/assets/373dd390-2093-4c12-9c84-5fd058cdf1a7" />

**Create a new branches for planned change**
Khi tạo nhánh mới mình sẽ đặt tên, nhánh mới này có nội dung copy của nhánh main.
Để tạo 1 nhánh mới trên giao diện Github:
1. Chọn drop down main
2. Đặt tên nhánh, như trong hình là myFirstBranch và nhấn create

**Merging branch:**
<img width="774" height="507" alt="image" src="https://github.com/user-attachments/assets/f37dc4f0-96a8-41d0-80be-c2145f5464fb" />

### 1. Nhánh chính (Main Branch)
- **Khái niệm:** Là nhánh mặc định, lưu trữ phiên bản code đã hoàn thiện và có thể triển khai (deployable version).
- **Vai trò:** Đây là nguồn dữ liệu chuẩn nhất của dự án. Mọi thay đổi đều bắt nguồn từ đây và cuối cùng sẽ quay về đây.

### 2. Nhánh phụ & Quy trình thay đổi (Branching Workflow)
Khi bạn muốn thay đổi code hoặc thêm tính năng:
- **Tạo nhánh mới:** Bạn tạo một nhánh mới từ main với một cái tên có ý nghĩa (descriptive name).
- **Bản sao ban đầu:** Nhánh mới bắt đầu như một bản sao chính xác (exact copy) của nhánh gốc tại thời điểm đó.
- **Làm việc độc lập:** Bạn có thể thay đổi file, sửa lỗi trên nhánh này mà không sợ làm hỏng code ở nhánh main. Nhiều người có thể làm việc trên nhiều nhánh khác nhau cùng một lúc (simultaneously).

### 3. Commit - Ghi nhận thay đổi
- **Ý nghĩa:** Commit thể hiện rằng lập trình viên tin tưởng code của họ đã đạt đến trạng thái ổn định (stable platform).
- **Lời nhắn (Commit Comment):** Phải mang tính mô tả và ý nghĩa.
- **Quy tắc viết (Best Practices):**
  - Không kết thúc bằng dấu chấm.
  - Độ dài dưới 50 ký tự (phần chi tiết ghi ở cửa sổ mở rộng).
  - Dùng thể chủ động (active voice).

### 4. Pull Request (PR) - Đề nghị gộp code
Đây là bước "kiểm duyệt" cực kỳ quan trọng trong làm việc nhóm:
- **Mục đích:** Đưa những thay đổi bạn đã commit cho người khác xem xét (review) và sử dụng.
- **Tính minh bạch:** GitHub lưu lại lịch sử không thể thay đổi (immutable logs), giúp xác định ai là người đã phê duyệt (approve) việc gộp code.
- **Tự động hóa:** GitHub sẽ tự tạo PR nếu bạn thay đổi code trên một nhánh mà bạn không sở hữu (ví dụ khi bạn Fork).

### 5. Merge - Gộp code vào Main
- **Quy trình:** Sau khi PR được xem xét và phê duyệt, code từ nhánh phụ sẽ được gộp ngược lại vào nhánh chính.
- **Lệnh thực hiện:** Merge pull request -> Confirm merge.
- **Dọn dẹp:** Khi một nhánh đã hoàn thành nhiệm vụ và được merge, nó trở nên lỗi thời (obsolete) và nên bị xóa bỏ.

## To sum up:
- Main branch contains the finished, deployable version of the code.
- New branches are created to change code.
- Created branch holds the changed code.
- Changes are saved using commits.
- Pull requests are used to share code changes for review.
- When the code is ready to deploy, merge it back into main.
