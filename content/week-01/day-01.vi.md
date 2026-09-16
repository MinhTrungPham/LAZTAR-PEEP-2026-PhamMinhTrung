+++

#### I. Các câu lệnh Git cơ bản

title = "Ngày 01 - 15/09/2026"
weight = 1
+++

## Topics Learned

### Git

#### Các câu lệnh phổ biến

| Lệnh         | Mô Tả                                            |
| ------------ | ------------------------------------------------ |
| git init     | Khởi tạo kho lưu trữ Git mới                     |
| git remote   | Quản lý kết nối kho lưu trữ từ xa                |
| git clone    | Sao chép kho lưu trữ từ xa về máy cục bộ         |
| git fetch    | Tải các thay đổi từ xa mà không hợp nhất         |
| git pull     | Tải và hợp nhất các thay đổi từ xa               |
| git status   | Hiển thị trạng thái hiện tại của kho lưu trữ     |
| git branch   | Liệt kê, tạo hoặc xóa các nhánh                  |
| git switch   | Chuyển sang nhánh khác                           |
| git checkout | Chuyển nhánh hoặc khôi phục tệp thư mục làm việc |
| git add      | Chuẩn bị các thay đổi để commit                  |

#### Ảnh chụp các câu lệnh Git

![Câu lệnh git version](/images/tuan1/day-01/git_version.png)
![Câu lệnh git init](/images/tuan1/day-01/git_init.png)
![Câu lệnh git remote](/images/tuan1/day-01/git_remote.png)
![Câu lệnh git clone](/images/tuan1/day-01/git_clone.png)
![Câu lệnh git fetch](/images/tuan1/day-01/git_fetch.png)
![Câu lệnh git pull](/images/tuan1/day-01/git_pull.png)
![Câu lệnh git status](/images/tuan1/day-01/git_status.png)
![Câu lệnh git branch](/images/tuan1/day-01/git_branch.png)
![Câu lệnh git switch](/images/tuan1/day-01/git_switch.png)
![Câu lệnh git checkout](/images/tuan1/day-01/git_checkout.png)
![Câu lệnh git add](/images/tuan1/day-01/git_add.png)
![Câu lệnh git commit](/images/tuan1/day-01/git_commit.png)
![Câu lệnh git commit và git log](/images/tuan1/day-01/git_commit_git_log.png)
![Câu lệnh git commit amend](/images/tuan1/day-01/git_amend.png)
![Câu lệnh git push](/images/tuan1/day-01/git_push.png)
![Câu lệnh git reset](/images/tuan1/day-01/git_reset.png)
![Câu lệnh git stash](/images/tuan1/day-01/git%20stash.png)
![Câu lệnh git stash pop](/images/tuan1/day-01/git_stash_pop.png)
![Câu lệnh git merge](/images/tuan1/day-01/git_merge.png)
| git commit | Ghi lại các thay đổi vào kho lưu trữ |
| git commit --amend | Sửa đổi commit cuối cùng |
| git push | Tải các commit cục bộ lên từ xa |
| git reset | Bỏ chuẩn bị hoặc đặt lại các commit |
| git rebase | Áp dụng lại các commit trên một nhánh khác |
| git rebase -i | Rebase tương tác để chỉnh sửa các commit |
| git stash | Lưu các thay đổi chưa commit tạm thời |
| git stash pop | Khôi phục các thay đổi đã lưu trữ |
| git merge | Kết hợp các thay đổi từ nhánh khác |
| git cherry-pick | Áp dụng các commit cụ thể từ nhánh khác |

#### Xử Lý Xung Đột Git

| Tình Huống                                | Giải Pháp (Source Control)                                                                         |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Giữ lại thay đổi từ cả hai nhánh          | Mở tệp trong trình soạn thảo, chỉnh sửa thủ công để bao gồm cả hai thay đổi, rồi nhập vào dấu ✓    |
| Giữ lại thay đổi từ nhánh hiện tại        | Di chuột qua dấu xung đột và nhập nút "Accept Current Change"                                      |
| Giữ lại thay đổi từ nhánh đến             | Di chuột qua dấu xung đột và nhập nút "Accept Incoming Change"                                     |
| Hủy hợp nhất và bắt đầu lại               | Nhập biểu tượng Source Control ở thanh bên, rồi nhập menu "..." và chọn "Abort Merge"              |
| Giải quyết xung đột trong trình soạn thảo | Xung đột được đánh dấu bằng màu sắc, chỉnh sửa thủ công hoặc sử dụng giao diện giải quyết xung đột |

---

#### II. Thực hành Git cơ bản

> **Mục tiêu:** Tạo nhánh → Commit → Tạo Pull Request → Merge, và xử lý xung đột đơn giản.

---

**Bước 1 — Khởi tạo repository mới tên `git-practice`**

Tạo repository trên GitHub với cài đặt mặc định.

![Tạo repository mới trên GitHub](/images/tuan1/day-01/image.png)
![Repository đã được tạo thành công](/images/tuan1/day-01/image-1.png)

---

**Bước 2 — Clone repository về máy cục bộ**

Dùng `git clone` để tải repository trống về máy.

![Clone repository về máy cục bộ](/images/tuan1/day-01/image-2.png)

---

**Bước 3 — Tạo `README.md` trên `main`, commit và push**

Khởi tạo dự án với file `README.md`, sau đó commit và push lên nhánh `main`.

![Tạo README.md, commit và push lên main](/images/tuan1/day-01/image-3.png)

---

**Bước 4 — Tạo hai nhánh, chỉnh sửa, push và tạo Pull Request**

Tạo hai nhánh riêng biệt từ `main`, mỗi nhánh có thay đổi khác nhau trong `README.md`. Push cả hai nhánh và tạo Pull Request cho từng nhánh.

![Tạo nhánh và thực hiện thay đổi](/images/tuan1/day-01/image-4.png)
![Push nhánh và tạo Pull Request (nhánh 1)](/images/tuan1/day-01/image-5.png)
![Push nhánh và tạo Pull Request (nhánh 2)](/images/tuan1/day-01/image-6.png)
![Danh sách Pull Request trên GitHub](/images/tuan1/day-01/image-7.png)

---

**Bước 5 — Tạo và giải quyết xung đột merge**

Khi hai nhánh cùng chỉnh sửa một dòng, xung đột sẽ xảy ra khi merge. Giải quyết thủ công và hoàn tất quá trình merge.

![Phát hiện xung đột khi merge](/images/tuan1/day-01/image-8.png)
![Giải quyết xung đột trong trình soạn thảo](/images/tuan1/day-01/image-9.png)
![Xung đột đã được giải quyết, merge hoàn tất](/images/tuan1/day-01/image-10.png)
