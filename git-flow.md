# Quy trình Làm việc với Git và GitHub (Workflow)

Tài liệu này tổng hợp các bước cơ bản để quản lý mã nguồn, cộng tác nhóm và hiểu về luồng của một dự án phần mềm sử dụng Git.

---

## 1. Kết nối và Đồng bộ
Một khi đã có kết nối giữa **Local Repo** (máy cá nhân) và **Remote Repo** (trên GitHub/GitLab), chúng ta có thể dễ dàng đồng bộ hóa dữ liệu:
<img width="896" height="421" alt="image" src="https://github.com/user-attachments/assets/a75314d7-8399-4e2d-b014-91bdd62a415a" />

* **Push:** Đẩy các thay đổi từ máy cá nhân lên máy chủ.
* **Pull:** Lấy code mới nhất từ máy chủ về máy cá nhân để cập nhật.
<img width="900" height="392" alt="image" src="https://github.com/user-attachments/assets/54f1519b-ce7c-4c0d-80fe-1bc67fb0929d" />

## 2. Quản lý Nhánh (Branching)
Nếu không muốn các thay đổi ảnh hưởng đến nhánh chính (`main`), cách tốt nhất là tạo một nhánh mới.
<img width="890" height="279" alt="image" src="https://github.com/user-attachments/assets/6d040fdb-18f7-4ae5-a38a-a27da5fdb944" />

* **Khái niệm:** Một nhánh trong Git là một không gian phát triển riêng biệt.
* **Lợi ích:** Bạn có thể tự do thử nghiệm, thêm tính năng mà không lo làm hỏng mã nguồn đang chạy ổn định trên nhánh `main`.

## 3. Quy trình Lưu trữ Thay đổi (Committing)
Sau khi hoàn thiện một tính năng (feature), bạn thực hiện lưu trữ theo các bước:
<img width="894" height="258" alt="image" src="https://github.com/user-attachments/assets/db6654f2-bb26-41e4-9eb1-f30761c66961" />

### Bước 1: Staging Area
* Chọn các file vừa thay đổi và chuyển đến **Staging Area**.
* Đây là khu vực lưu trữ tạm thời để bạn kiểm tra lại danh sách các file trước khi Git lưu chúng vào lịch sử chính thức.
* Sau khi đã hoàn thiện 1 feature, chọn file vừa thay đổi và chuyển đến staging area.
The staging area is a temporary storage space where you collect the selected files ​before asking git to save them in the local repository. ​You can now commit the files to the newly created branch. 

​Committing files allows you to record the changes and ​ensure your new feature becomes a part of the branch. ​When you commit files, including a commit message provides context for you and ​your team members to understand the change. 
### Bước 2: Commit
* Ghi lại các thay đổi vào nhánh vừa tạo.
* **Commit Message:** Luôn bao gồm tin nhắn mô tả ngắn gọn để cung cấp ngữ cảnh cho chính bạn và đồng nghiệp hiểu mục đích của thay đổi này.

## 4. Gửi Đóng góp (Push & Pull Request)

### Đẩy code (Push)
The next step is pushing the changes in the branch to the remote repository.
<img width="882" height="316" alt="image" src="https://github.com/user-attachments/assets/f1d73d99-583d-42eb-b705-fb22b8bfca56" />

### Kiểm duyệt mã nguồn (Reviewing Code)
* Most often, the code is reviewed by a maintainer who is responsible for managing ​the repository before it is merged into the main branch in the remote repository. ​To merge the branch, you create a pull request. ​It is a request to the maintainer to review and ​approve the changes in the branch. 
​After the maintainer merges the pull request, ​the changes in the branch will be reflected in the main branch. ​Similarly, if you have maintainer access, you will receive pull requests from ​your team members and you will review and approve their requests. ​You learned about the typical workflow in a software development project.
* Mã nguồn thường được kiểm duyệt bởi **Maintainer** (người quản lý kho lưu trữ) trước khi được gộp vào nhánh chính.
* **Pull Request (PR):** Đây là yêu cầu gửi tới Maintainer để họ xem xét, thảo luận và phê duyệt các thay đổi của bạn.
<img width="899" height="329" alt="image" src="https://github.com/user-attachments/assets/c99d8083-485a-4c25-b4fb-b553f3dd23b2" />

> [!IMPORTANT]
> **Lưu ý thuật ngữ:** Không có khái niệm "Push Request".
> * Luôn đứng từ góc nhìn của Maintainer: Họ sẽ kéo code của bạn về (**Pull**) để kiểm tra và gộp (**Merge**).
> * **Pull Request:** Dùng cho GitHub.
> * **Merge Request:** Dùng cho GitLab.

## 5. Nếu bạn bắt đầu dự án từ đầu và muốn cộng tác với người khác: 

1.  **Initialize:** Khởi tạo thư mục dự án thành một Git Repository (`git init`).
2.  **Add & Commit:** Chọn tất cả các file dự án, đưa vào Staging Area và thực hiện commit đầu tiên (*Initial Commit*).
3.  **Link Remote:** Tạo một repository trống trên GitHub và liên kết với local repository của bạn.
4.  **Push:** Đẩy code lên để mọi người cùng bắt đầu cộng tác.

## 6. Khi bạn tham gia vào một dự án đã có sẵn:

* **Clone:** Tải Remote Repo về máy.
* **Branch:** Tạo nhánh mới và làm việc trên đó.
* **Stage & Commit:** Đưa file vào Staging Area và lưu lại thay đổi.
* **Push:** Đẩy nhánh đó lên Remote Repo.
* **Pull Request:** Tạo yêu cầu để merge nhánh của bạn vào nhánh `main`.
## Đọc thêm.
* Giai đoạn Web application development.
<img width="927" height="475" alt="image" src="https://github.com/user-attachments/assets/a7e764b7-1732-4b98-8d1e-721bfe5b6dba" />

* Giai đoạn  feature development.
<img width="896" height="475" alt="image" src="https://github.com/user-attachments/assets/6d6093c2-9a64-4ce7-8168-266ab4e2f668" />

* Giai đoạn Project release
<img width="922" height="473" alt="image" src="https://github.com/user-attachments/assets/732088a0-8a9e-4f12-8306-afcd598fc4a4" />
