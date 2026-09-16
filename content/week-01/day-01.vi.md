+++

#### I. Các câu lệnh Git cơ bản

title = "Ngày 01 - 15/09/2026"
weight = 1
+++

## Topics Learned

### Git

#### Các câu lệnh phổ biến

| Lệnh        | Mô Tả                                                    |
| ------------ | ---------------------------------------------------------- |
| git init     | Khởi tạo kho lưu trữ Git mới                          |
| git remote   | Quản lý kết nối kho lưu trữ từ xa                   |
| git clone    | Sao chép kho lưu trữ từ xa về máy cục bộ           |
| git fetch    | Tải các thay đổi từ xa mà không hợp nhất          |
| git pull     | Tải và hợp nhất các thay đổi từ xa                 |
| git status   | Hiển thị trạng thái hiện tại của kho lưu trữ      |
| git branch   | Liệt kê, tạo hoặc xóa các nhánh                     |
| git switch   | Chuyển sang nhánh khác                                  |
| git checkout | Chuyển nhánh hoặc khôi phục tệp thư mục làm việc |
| git add      | Chuẩn bị các thay đổi để commit                     |

#### Ảnh chụp các câu lệnh Git

**`git version`** — Kiểm tra phiên bản Git đang được cài đặt trên máy.

![Câu lệnh git version](/images/tuan1/day-01/git_version.png)

**`git init`** — Khởi tạo một kho lưu trữ Git mới tại thư mục hiện tại.

![Câu lệnh git init](/images/tuan1/day-01/git_init.png)

**`git remote`** — Xem và quản lý các kết nối đến kho lưu trữ từ xa.

![Câu lệnh git remote](/images/tuan1/day-01/git_remote.png)

**`git clone`** — Sao chép một kho lưu trữ từ xa về máy cục bộ.

![Câu lệnh git clone](/images/tuan1/day-01/git_clone.png)

**`git fetch`** — Tải các thay đổi từ remote về mà không hợp nhất vào nhánh hiện tại.

![Câu lệnh git fetch](/images/tuan1/day-01/git_fetch.png)

**`git pull`** — Tải và hợp nhất ngay các thay đổi từ remote vào nhánh hiện tại.

![Câu lệnh git pull](/images/tuan1/day-01/git_pull.png)

**`git status`** — Hiển thị các file đã stage, chưa stage hoặc chưa được theo dõi trong thư mục làm việc.

![Câu lệnh git status](/images/tuan1/day-01/git_status.png)

**`git branch`** — Liệt kê tất cả các nhánh cục bộ; nhánh đang hoạt động được tô sáng.

![Câu lệnh git branch](/images/tuan1/day-01/git_branch.png)

**`git switch`** — Chuyển sang nhánh khác mà không ảnh hưởng đến các thay đổi chưa commit.

![Câu lệnh git switch](/images/tuan1/day-01/git_switch.png)

**`git checkout`** — Chuyển nhánh hoặc khôi phục một file về trạng thái cũ.

![Câu lệnh git checkout](/images/tuan1/day-01/git_checkout.png)

**`git add`** — Đưa các thay đổi vào vung stage để chuẩn bị cho commit tiếp theo.

![Câu lệnh git add](/images/tuan1/day-01/git_add.png)

**`git commit`** — Lưu các thay đổi đã stage thành một snapshot mới trong lịch sử kho lưu trữ.

![Câu lệnh git commit](/images/tuan1/day-01/git_commit.png)

**`git commit` + `git log`** — Sau khi commit, dùng `git log` để xem lịch sử commit và xác nhận entry mới.

![Câu lệnh git commit và git log](/images/tuan1/day-01/git_commit_git_log.png)

**`git commit --amend`** — Chỉnh sửa thông điệp commit gần nhất hoặc bổ sung thêm thay đổi đã stage.

![Câu lệnh git commit amend](/images/tuan1/day-01/git_amend.png)

**`git push`** — Tải các commit cục bộ lên nhánh tương ứng trên kho lưu trữ từ xa.

![Câu lệnh git push](/images/tuan1/day-01/git_push.png)

**`git reset`** — Bỏ stage các file hoặc di chuyển con trỏ nhánh về một commit trước.

![Câu lệnh git reset](/images/tuan1/day-01/git_reset.png)

**`git stash`** — Lưu tạm các thay đổi chưa commit để thư mục làm việc sạch sẽ.

![Câu lệnh git stash](/images/tuan1/day-01/git%20stash.png)

**`git stash pop`** — Áp dụng lại các thay đổi được lưu mới nhất và xóa khỏi danh sách stash.

![Câu lệnh git stash pop](/images/tuan1/day-01/git_stash_pop.png)

**`git merge`** — Hợp nhất lịch sử của một nhánh khác vào nhánh hiện tại.

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

| Tình Huống                                     | Giải Pháp (Source Control)                                                                                              |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| Giữ lại thay đổi từ cả hai nhánh          | Mở tệp trong trình soạn thảo, chỉnh sửa thủ công để bao gồm cả hai thay đổi, rồi nhập vào dấu ✓       |
| Giữ lại thay đổi từ nhánh hiện tại       | Di chuột qua dấu xung đột và nhập nút "Accept Current Change"                                                      |
| Giữ lại thay đổi từ nhánh đến            | Di chuột qua dấu xung đột và nhập nút "Accept Incoming Change"                                                     |
| Hủy hợp nhất và bắt đầu lại              | Nhập biểu tượng Source Control ở thanh bên, rồi nhập menu "..." và chọn "Abort Merge"                           |
| Giải quyết xung đột trong trình soạn thảo | Xung đột được đánh dấu bằng màu sắc, chỉnh sửa thủ công hoặc sử dụng giao diện giải quyết xung đột |

---

#### II. Thực hành Git cơ bản

> **Mục tiêu:** Tạo nhánh → Commit → Push → Pull Request → Merge → Xử lý conflict.

---

**Bước 1 — Tạo repository mới tên `git-practice`**

Tạo một repository public mới trên GitHub tên `git-practice`. Không cần tạo README.md trền GitHub — file này sẽ được thêm ở local.

![Tạo repository mới trên GitHub](/images/tuan1/day-01/create_new_repo1.png)

![Repository đã được tạo thành công](/images/tuan1/day-01/create_new_repo2.png)

---

**Bước 2 — Clone repository về máy cục bộ**

Clone repository trống về máy, di chuyển vào thư mục dự án, và kiểm tra kết nối remote:

```bash
git clone https://github.com/<username>/git-practice.git
cd git-practice
git status
git remote -v
```

![Clone repository và kiểm tra remote](/images/tuan1/day-01/git_clone_new_repo.png)

---

**Bước 3 — Tạo `README.md`, commit và push lên `main`**

Tạo `README.md` với nội dung ngắn, stage, commit và push:

```bash
"# Git Practice" | Out-File README.md

git add README.md
git commit -m "Initial README"
git push -u origin main
```

![Stage, commit và push README.md lên main](/images/tuan1/day-01/git_add_commit_push.png)

---

**Bước 4 — Tạo nhánh 1: `feature/header`**

Tạo `feature/header` từ `main`, thêm section `## Header` vào `README.md`, sau đó push:

```bash
git switch -c feature/header
```

```markdown
## Header

Welcome to Git Practice.
```

```bash
git add README.md
git commit -m "Add header section"
git push -u origin feature/header
```

![Tạo feature/header và push](/images/tuan1/day-01/create_new_branch.png)

---

**Bước 5 — Tạo Pull Request 1**

Trên GitHub, mở PR từ `feature/header` vào `main`. **Chưa merge** — việc merge PR này là điều kiện để tạo conflict ở các bước sau.

![PR 1 đã được tạo](/images/tuan1/day-01/create_pull_request.png)

---

**Bước 6 — Tạo nhánh 2: `feature/description`**

> ⚠️ Chuyển về `main` trước. Nhánh 2 phải được tạo từ `main`, không phải từ `feature/header`.

```bash
git switch main
git pull origin main
git switch -c feature/description
```

![Tạo feature/description từ main](/images/tuan1/day-01/create_new_branch_from_main.png)

---

**Bước 7 — Chỉnh sửa cùng một dòng (cố ý tạo conflict)**

Trên `feature/description`, thay đổi dòng description của `README.md` thành nội dung khác so với `feature/header`. Cả hai nhánh bây giờ có nội dung bất đồng trên chính xác cùng một dòng — đó là nguyên nhân gây conflict.

```
Trước: This repository is used to practice basic Git workflows.
Sau:   This repository demonstrates Git workflows for developers.
```

---

**Bước 8 — Commit và push nhánh 2**

```bash
git add README.md
git commit -m "Update repository description"
git push -u origin feature/description
```

![Commit và push feature/description](/images/tuan1/day-01/modify_readme_push.png)

---

**Bước 9 — Tạo Pull Request 2**

Mở PR thứ hai từ `feature/description` vào `main`. Lúc này có hai PR đang chờ:

| PR | Nhánh                  | Target   |
| -- | ----------------------- | -------- |
| #1 | `feature/header`      | `main` |
| #2 | `feature/description` | `main` |

![PR 2 đã được tạo](/images/tuan1/day-01/create_pull_request_2.png)

---

**Bước 10 — Merge Pull Request 1**

PR #1 không có conflict — merge nó. Sau khi merge, `main` đã có section `## Header`.

![Merge Pull Request 1](/images/tuan1/day-01/merge_pull_request1.png)

---

**Bước 11 — Phát hiện conflict trên Pull Request 2**

Vì `main` đã thay đổi sau khi PR #1 được merge, GitHub đánh dấu PR #2 có conflict. Cùng một dòng bị chỉnh sửa khác nhau trên hai nhánh.

![Conflict phát hiện trên PR 2](/images/tuan1/day-01/conflict_on_pull_request2.png)

---

**Bước 12 — Tại sao conflict xảy ra**

Cả hai nhánh bắt đầu từ cùng một commit gốc nhưng mỗi nhánh chỉnh sửa cùng một dòng:

- `feature/header` → giữ description cũ, thêm `## Header`
- `feature/description` → viết lại dòng description

Git không tự chọn được phương án nào, nên dừng lại để cần xử lý thủ công.

---

**Bước 13 — Chuẩn bị giải quyết ở local**

Chuyển sang `feature/description` và lấy trạng thái mới nhất của remote:

```bash
git switch feature/description
git fetch origin
```

---

**Bước 14 — Kích hoạt conflict ở local**

Merge `origin/main` vào nhánh hiện tại. Git dừng lại và báo conflict:

```bash
git merge origin/main
```

```
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

![Conflict xuất hiện trong terminal](/images/tuan1/day-01/conflict_content.png)

---

**Bước 15 — Kiểm tra conflict trong VS Code**

Mở dự án trong VS Code. Bên trong `README.md`, Git đã chèn các marker thể hiện cả hai phiên bản:

```
<<<<<<< HEAD
This repository demonstrates Git workflows for developers.
=======
This repository is used to practice basic Git workflows.

## Header

Welcome to Git Practice.
>>>>>>> origin/main
```

- Phần giữa `<<<<<<< HEAD` và `=======` là nội dung từ nhánh hiện tại.
- Phần giữa `=======` và `>>>>>>> origin/main` là nội dung từ `main`.

![Conflict marker hiển thị trong VS Code](/images/tuan1/day-01/conflict_in_VSCode.png)

---

**Bước 16 — Giải quyết conflict**

Tự chỉnh sửa file để giữ lại cả description mới lẫn header section. Xóa tất cả các dòng marker sau khi xong.

```markdown
# Git Practice

This repository demonstrates Git workflows for developers.

## Header

Welcome to Git Practice.
```

VS Code có **Merge Editor** để so sánh song song nếu cần:

![Merge Editor trong VS Code](/images/tuan1/day-01/Resolve_in_merge_editor.png)

---

**Bước 17 — Stage, commit và push**

Sau khi lưu file, stage file đã giải quyết, tạo merge commit và push:

```bash
git add README.md
git commit -m "Resolve merge conflict in README"
git push origin feature/description
```

![Merge commit hoàn tất](/images/tuan1/day-01/Complete%20Merge.png)

![Push lên remote](/images/tuan1/day-01/push_conflict_resolve.png)

---

**Bước 18 — Conflict đã được xóa trên GitHub**

PR #2 trên GitHub lúc này không còn conflict và sẵn sàng merge.

![Conflict đã giải quyết trên PR 2](/images/tuan1/day-01/Conflict%20Resolved%20on%20Pull%20Request.png)

---

**Bước 19 — Merge Pull Request 2**

Merge PR #2 vào `main` trên GitHub.

![Pull Request 2 đã được merge](/images/tuan1/day-01/Pull%20Request%202%20Merged.png)

---

**Bước 20 — Kiểm tra kết quả cuối**

Pull `main` mới nhất và xác nhận nội dung:

```bash
git switch main
git pull origin main
git log --oneline --graph --all
```

```markdown
# Git Practice

This repository demonstrates Git workflows for developers.

## Header

Welcome to Git Practice.
```

![Trạng thái cuối cùng của repository](/images/tuan1/day-01/Final%20Repository.png)
