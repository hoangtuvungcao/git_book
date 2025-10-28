<div align="center">

# HƯỚNG DẪN TOÀN DIỆN GIT & GITHUB

</div>

## MỤC LỤC
1. [Giới thiệu](#1-giới-thiệu--tổng-quan-phân-tích-chi-tiết)
2. [Cài đặt Git](#2-cài-đặt-git-phân-tích--thực-hành)
3. [Thiết lập Git lần đầu](#3-cấu-hình-git-ban-đầu-phân-tích-chi-tiết)
4. [Giải thích chi tiết các lệnh Git (đầy đủ nhất)](#4-giải-thích-đầy-đủ-các-lệnh-git-phổ-biến-phân-tích--ví-dụ)
5. [Làm việc với GitHub](#5-làm-việc-với-github-từ-cơ-bản-đến-nâng-cao)
6. [Kết nối GitHub: SSH & HTTPS](#6-kết-nối-github-với-git-ssh-vs-https-đầy-đủ-chi-tiết)
7. [Lỗi thường gặp & cách khắc phục](#7-lỗi-thường-gặp--cách-khắc-phục-phân-tích-sâu)
8. [Teamwork & workflow nhóm](#8-làm-việc-nhóm-với-git--github-teamwork-chuyên-nghiệp)
9. [Lệnh nâng cao, mẹo & công cụ hỗ trợ](#9-lệnh-nâng-cao-mẹo--công-cụ-hỗ-trợ-phân-tích)
10. [Tài nguyên tham khảo](#10-tài-nguyên-tham-khảo--lộ-trình-học)
11. [Kết Luận & Gợi Ý Duy Trì ](#11-kết-luận--gợi-ý-duy-trì)
12. [Giấy Phép](#12-giấy-phép)

>  **Cách sử dụng mục lục:** Bấm vào từng mục để chuyển nhanh đến nội dung tương ứng. Dùng phím *Back* của trình duyệt (hoặc tổ hợp `Alt + ←`) để quay lại mục lục. Bạn có thể tìm nhanh bằng `Ctrl + F` với từ khóa quan tâm.

## 1. GIỚI THIỆU & TỔNG QUAN (PHÂN TÍCH CHI TIẾT)

### Git là gì? (Phân tích)
- Git là hệ thống quản lý phiên bản phân tán (DVCS) cho phép nhiều người cùng làm việc, lưu lại lịch sử thay đổi, dễ dàng phục hồi, thử nghiệm, phát triển song song.
- **Ứng dụng:** Quản lý code, tài liệu, dữ liệu, hợp tác nhóm, open source, CI/CD.
- **Ví dụ thực tế:** Một nhóm phát triển phần mềm có thể làm việc trên nhiều tính năng cùng lúc, mỗi người một nhánh, khi xong hợp nhất lại.

### GitHub là gì? (Phân tích)
- GitHub là nền tảng lưu trữ, chia sẻ mã nguồn dựa trên Git, cung cấp giao diện web, quản lý issue, review code, CI/CD, bảo mật, cộng đồng lớn.
- **So sánh:** Ngoài GitHub còn có GitLab, Bitbucket, Gitea... nhưng GitHub nổi bật về cộng đồng và tích hợp open source.
- **Ví dụ:** Các dự án lớn như Linux, VSCode, React... đều public trên GitHub.

### Ứng dụng thực tế của Git/GitHub
- Quản lý dự án phần mềm, website, tài liệu, bài báo khoa học, data science, devops, v.v.
- Làm việc nhóm từ startup đến enterprise.
- Đóng góp open source, xây dựng thương hiệu cá nhân.
- **Nhận xét:** Git/GitHub là tiêu chuẩn toàn cầu cho phát triển phần mềm hiện đại.

### Các mô hình sử dụng phổ biến
- **Cá nhân:** Quản lý code, backup, thử nghiệm, học tập.
- **Nhóm nhỏ:** Teamwork, chia branch, review code, quản lý tiến độ.
- **Doanh nghiệp:** Quy trình CI/CD, bảo mật, phân quyền, audit, release, compliance.
- **Open source:** Fork, Pull Request, Issue, Project, Discussion, cộng đồng đóng góp.
- **Lưu ý:** Mỗi mô hình sẽ có workflow, quy tắc, chiến lược khác nhau.

### Lợi ích khi dùng Git/GitHub (Phân tích)
- **Lịch sử thay đổi:** Có thể quay lại bất kỳ thời điểm nào, phục hồi code cũ.
- **Teamwork hiệu quả:** Tránh ghi đè code, hỗ trợ review, kiểm soát chất lượng.
- **Minh bạch:** Dễ kiểm soát, audit, trace lỗi, truy vết trách nhiệm.
- **Tích hợp công cụ:** Tự động kiểm tra, build, deploy (CI/CD), bảo mật, test.
- **Cộng đồng:** Dễ học hỏi, chia sẻ, đóng góp, xây dựng thương hiệu cá nhân.

### Nhược điểm (Phân tích)
- **Đòi hỏi học cú pháp:** Lệnh dòng lệnh nhiều, dễ nhầm khi mới học.
- **Xung đột merge:** Nếu teamwork không tốt, dễ gặp conflict khó xử lý.
- **Tính năng nâng cao:** (rebase, cherry-pick...) có thể gây mất code nếu không hiểu rõ.
- **Bảo mật:** Nếu không cẩn thận có thể lộ dữ liệu nhạy cảm (token, mật khẩu).

### Các khái niệm quan trọng (Giải thích)
- **Repository (repo):** Kho lưu trữ mã nguồn, có thể local hoặc remote.
- **Commit:** Ghi lại một thay đổi, gồm nội dung, tác giả, thời gian, thông điệp.
- **Branch:** Nhánh phát triển song song, giúp phát triển nhiều tính năng độc lập.
- **Merge:** Hợp nhất nhánh, kết hợp thay đổi từ nhiều nguồn.
- **Pull Request:** Đề xuất hợp nhất code (review, thảo luận trước khi merge).
- **Fork:** Sao chép repo về tài khoản cá nhân để phát triển độc lập.
- **Remote:** Kho lưu trữ trên server (GitHub, GitLab, ...).
- **Staging area:** Khu vực chuẩn bị commit, kiểm soát file nào sẽ được ghi lại.
- **Tag:** Đánh dấu các phiên bản quan trọng.

### So sánh Git với các hệ thống khác (Bảng phân tích)
| Tiêu chí              | Git (với GitHub) | SVN            | Mercurial     |
|----------------------|------------------|---------------|--------------|
| Kiểu quản lý         | Phân tán         | Tập trung      | Phân tán      |
| Hỗ trợ branch/merge  | Mạnh mẽ           | Yếu            | Tốt           |
| Tốc độ               | Nhanh            | Trung bình     | Nhanh         |
| Cộng đồng            | Rất lớn          | Đang giảm      | Nhỏ           |
| Dễ học               | Trung bình       | Dễ             | Dễ            |
| Tích hợp CI/CD       | Rất mạnh         | Yếu            | Trung bình    |
| Phù hợp open source  | Tuyệt vời        | Không phổ biến | Thấp          |

**Nhận xét:** Git gần như đã thay thế các hệ thống khác trong phát triển phần mềm hiện đại.

### Lưu ý chiến lược khi dùng Git/GitHub (Tư duy thực tế)
- **Luôn commit nhỏ, ghi chú rõ ràng:** Dễ review, rollback, trace lỗi.
- **Push code thường xuyên:** Tránh mất dữ liệu, dễ backup, dễ làm việc nhóm.
- **Sử dụng branch cho từng tính năng/bugfix:** Tránh xung đột, dễ kiểm soát tiến độ.
- **Review code trước khi merge:** Đảm bảo chất lượng, phát hiện bug sớm.
- **Tuân thủ workflow nhóm:** Quy định rõ quy trình, phân quyền, kiểm soát truy cập.
- **Bảo mật:** Không push file nhạy cảm, dùng .gitignore, quét secret tự động.
- **Tận dụng tài nguyên cộng đồng:** Học hỏi, đóng góp, xây dựng profile cá nhân.

---

## 2. CÀI ĐẶT GIT (PHÂN TÍCH & THỰC HÀNH)
### 2.0. Lựa chọn phiên bản phù hợp
- Git hiện hỗ trợ hầu hết hệ điều hành. Chọn bản cài đặt **Stable/LTS** để đảm bảo ổn định.
- Có thể kiểm tra phiên bản mới nhất tại https://git-scm.com/downloads. Một số doanh nghiệp khuyến nghị bản cụ thể để tương thích CI/CD.

### 2.1. Windows
- Tải tại https://git-scm.com/download/win (tự động nhận diện 32/64-bit).
- Khi chạy file `.exe`, lưu ý các bước quan trọng:
  1. **Select Components:** Giữ nguyên "Git Bash" và "Git GUI"; có thể tick thêm "Windows Explorer integration" để mở Git nhanh từ menu chuột phải.
  2. **Choosing the default editor:** Tuỳ chọn VSCode, Vim hoặc editor ưa thích.
  3. **Adjusting PATH environment:** Chọn "Git from the command line and also from 3rd-party software" để dùng được Git trong mọi terminal.
  4. **HTTPS transport backend:** Nên chọn OpenSSL.
  5. **Line ending conversions:** Chọn "Checkout Windows-style, commit Unix-style" (mặc định) để tránh lỗi xuống dòng.
- Sau khi cài, mở **Command Prompt**, **PowerShell** hoặc **Git Bash** và kiểm tra:
  ```sh
  git --version
  where git
  ```
- Nếu `where git` không trả về đường dẫn, cần thêm `C:\Program Files\Git\cmd` vào biến môi trường PATH.

### 2.2. macOS
- Với người dùng đã cài **Homebrew**, chạy:
  ```sh
  brew install git
  ```
- Nếu không dùng Homebrew, tải file `.dmg` từ https://git-scm.com/download/mac hoặc dùng Xcode Command Line Tools:
  ```sh
  xcode-select --install
  ```
- Kiểm tra phiên bản và đường dẫn:
  ```sh
  git --version
  which git
  ```
- Nếu sử dụng nhiều phiên bản Git (ví dụ từ Xcode và Homebrew), hãy ưu tiên bản mới bằng cách thêm `/usr/local/bin` vào trước PATH.

### 2.3. Linux (Ubuntu/Debian)
```sh
sudo apt update
sudo apt install git
git --version
```
- Các bản phân phối khác:
  - **Fedora/CentOS/RHEL:** `sudo dnf install git` hoặc `sudo yum install git`.
  - **Arch Linux:** `sudo pacman -S git`.
  - **OpenSUSE:** `sudo zypper install git`.

### 2.4. Kiểm tra cấu hình terminal & proxy
- Đảm bảo terminal hỗ trợ UTF-8 để hiển thị tiếng Việt chính xác.
- Nếu làm việc sau proxy công ty, cấu hình:
  ```sh
  git config --global http.proxy http://user:pass@proxy:port
  git config --global https.proxy https://user:pass@proxy:port
  ```
- Có thể gỡ cấu hình proxy khi làm việc tại nhà:
  ```sh
  git config --global --unset http.proxy
  git config --global --unset https.proxy
  ```

### 2.5. Cập nhật Git
- **Windows/macOS:** Cài đè bản mới từ trang chủ hoặc dùng Homebrew (`brew upgrade git`).
- **Linux:** Sử dụng trình quản lý gói (`sudo apt upgrade git`).
- Kiểm tra phiên bản hiện tại:
  ```sh
  git --version
  ```

### 2.6. Cài đặt công cụ bổ trợ (khuyến nghị)
- **GitHub Desktop:** Dễ dùng cho người mới, hỗ trợ thao tác kéo thả.
- **Sourcetree/GitKraken:** Quản lý branch trực quan, mạnh cho teamwork.
- **VSCode + GitLens:** Xem lịch sử, blame, so sánh code ngay trong IDE.
- **WSL (Windows Subsystem for Linux):** Nếu cần môi trường Linux ngay trên Windows.

### 2.7. Xử lý sự cố cài đặt thường gặp
- **Không nhận lệnh `git`:** Kiểm tra PATH, khởi động lại terminal hoặc máy.
- **Lỗi chứng chỉ SSL khi kết nối GitHub:** Cài đặt/ cập nhật chứng chỉ CA hoặc dùng `git config --global http.sslBackend schannel` trên Windows.
- **Không gõ được tiếng Việt trong Git Bash:** Chuyển sang Windows Terminal/PowerShell hoặc thiết lập font hỗ trợ Unicode.
- **“fatal: unable to auto-detect email address”:** Thiếu cấu hình user (xem phần 3).

>  **Mẹo:** Sau khi cài xong, chạy `git help -g` để xem danh sách nhóm lệnh, hoặc `git help <command>` để đọc tài liệu chính thức ngay trên máy.

---

## 3. CẤU HÌNH GIT BAN ĐẦU (PHÂN TÍCH CHI TIẾT)

### 3.1. Thiết lập thông tin người dùng
- **Mục đích:** Git ghi lại tác giả của mỗi commit. Thiếu thông tin này sẽ bị báo lỗi khi commit.
- **Lệnh cấu hình toàn cục (global):**
  ```sh
  git config --global user.name "Tên của bạn"
  git config --global user.email "email@domain.com"
  ```
- **Lưu ý:**
  - Email nên trùng với email GitHub để hiển thị avatar đúng.
  - Có thể dùng email ẩn của GitHub (dạng `username@users.noreply.github.com`) để bảo mật.
  - Nếu cần cấu hình khác nhau cho từng dự án, bỏ `--global` và chạy trong repo tương ứng.

### 3.2. Thiết lập editor, diff, merge tool
- **Editor mặc định:**
  ```sh
  git config --global core.editor "code --wait"   # VSCode
  git config --global core.editor "vim"
  ```
- **Công cụ so sánh (diff) và merge:**
  ```sh
  git config --global merge.tool vscode
  git config --global diff.tool vscode
  ```
- **Ý nghĩa:** Khi gặp conflict, Git sẽ mở tool hỗ trợ giải quyết.

### 3.3. Kiểm tra cấu hình
- Xem toàn bộ cấu hình đang áp dụng:
  ```sh
  git config --list --show-origin
  ```
  - `--show-origin`: hiển thị file nguồn (global/local/system).
- Xem cấu hình cụ thể:
  ```sh
  git config user.name
  git config --global user.email
  ```

### 3.4. Các tệp cấu hình Git
- **Global (mặc định):** `~/.gitconfig`
- **System:** `/etc/gitconfig` (dùng cho toàn bộ máy).
- **Local (repo hiện tại):** `.git/config`
- Có thể chỉnh thủ công hoặc dùng lệnh `git config`.

### 3.5. Alias (lệnh rút gọn khuyến nghị)
```sh
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm "commit -m"
git config --global alias.last "log -1 --stat"
git config --global alias.lg "log --oneline --graph --decorate --all"
```
- **Lợi ích:** Gõ lệnh nhanh, hạn chế gõ sai.
- Có thể tuỳ chỉnh theo nhu cầu team (ghi vào `~/.gitconfig`).

### 3.6. Credential helper (lưu thông tin đăng nhập)
- **Windows:**
  ```sh
  git config --global credential.helper manager
  ```
- **macOS:**
  ```sh
  git config --global credential.helper osxkeychain
  ```
- **Linux:**
  ```sh
  git config --global credential.helper cache
  # Hoặc lưu vĩnh viễn:
  git config --global credential.helper store
  ```
- **Lưu ý:** `store` lưu plain text → chỉ dùng khi an toàn.

### 3.7. Thiết lập chuẩn hoá line ending & encoding
- **Line ending:**
  ```sh
  git config --global core.autocrlf true      # Windows
  git config --global core.autocrlf input     # macOS/Linux
  ```
- **Encoding:**
  ```sh
  git config --global i18n.commitencoding utf-8
  git config --global i18n.logoutputencoding utf-8
  ```
- Giúp tránh lỗi xuống dòng, hiển thị tiếng Việt sai.

### 3.8. Thiết lập mặc định branch chính (main/master)
- Git 2.28 trở lên cho phép đặt branch mặc định:
  ```sh
  git config --global init.defaultBranch main
  ```
- Giúp các repo mới dùng `main` thay vì `master`.

### 3.9. Bảo mật và tiện ích bổ sung
- **Quét secret tự động:**
  ```sh
  git config --global gpg.format ssh
  # Kết hợp GitHub secret scanning nếu dùng repo private.
  ```
- **Ký commit (GPG/SSH):** Tăng độ tin cậy commit.
- **Sử dụng `.gitignore_global`:**
  ```sh
  git config --global core.excludesfile ~/.gitignore_global
  ```
  - Thêm các file dùng chung (như .DS_Store, .idea, node_modules...).

### 3.10. Kiểm tra cấu hình sau khi set up
```sh
git config --list --show-origin
git config --global --edit   # Mở file global config để kiểm tra
```
- **Mẹo:** Lưu file cấu hình mẫu cho team để đồng bộ (share qua repo, wiki).

---
## 4. GIẢI THÍCH ĐẦY ĐỦ CÁC LỆNH GIT PHỔ BIẾN (PHÂN TÍCH & VÍ DỤ)

### 4.1. Khởi tạo repository mới
```sh
git init
```
- **Ý nghĩa:** Tạo thư mục ẩn `.git` để quản lý lịch sử dự án trong thư mục hiện tại.
- **Khi nào dùng:** Bắt đầu dự án mới, hoặc biến thư mục có sẵn thành repo.
- **Ví dụ:**
  ```sh
  mkdir myproject && cd myproject
  git init
  ```
- **Tuỳ chọn hữu ích:**
  ```sh
  git init --initial-branch=main  # Đặt tên branch mặc định ngay từ đầu
  git init --bare                 # Tạo repo trần (dùng làm remote nội bộ)
  ```
- **Lỗi hay gặp:** `fatal: not a git repository` → chưa chạy `git init` hoặc đang ở sai thư mục.
- **Ghi chú:** Sau khi init cần thêm remote (`git remote add origin ...`) trước khi push.

### 4.2. Nhân bản (clone) repository
```sh
git clone <url-repo>
```
- **Ý nghĩa:** Sao chép toàn bộ repo (code + lịch sử) về máy.
- **Khi nào dùng:** Lấy mã nguồn từ GitHub hoặc server nội bộ.
- **Ví dụ:**
  ```sh
  git clone https://github.com/username/project.git
  git clone git@github.com:username/project.git  # Dùng SSH
  ```
- **Tuỳ chọn:**
  ```sh
  git clone <url> <thu-muc>   # Đặt tên thư mục tuỳ ý
  git clone --branch develop <url>   # Clone nhánh cụ thể
  git clone --depth 1 <url>          # Clone nông, chỉ lấy commit mới nhất
  ```
- **Lưu ý bảo mật:** Khi clone bằng HTTPS sẽ yêu cầu tài khoản/token khi push.

### 4.3. Kiểm tra trạng thái file
```sh
git status
```
- **Ý nghĩa:** Cho biết file nào đang thay đổi, đã staged hay chưa.
- **Tip:** Dùng `git status -sb` để xem ngắn gọn (short + branch).
- **Thường dùng trước khi commit** để đảm bảo không bỏ sót file quan trọng.
- **Lỗi hay gặp:** File mong muốn không xuất hiện → kiểm tra `.gitignore`.

### 4.4. Thêm file vào Staging Area
```sh
git add <ten_file>
```
- **Ý nghĩa:** Đưa file vào khu vực staging, chuẩn bị commit.
- **Tình huống điển hình:** Chỉ chọn một số file thay vì toàn bộ.
- **Các biến thể hữu ích:**
  ```sh
  git add .                        # Thêm tất cả thay đổi
  git add src/**/*.dart            # Dùng glob pattern
  git add -p                       # Chọn từng hunk (phần) để add
  git add -u                       # Chỉ thêm file đã track (kể cả bị xoá)
  ```
- **Ghi chú:** Chỉ file đã staged mới được commit. Có thể kiểm tra bằng `git status`.

### 4.5. Ghi lại thay đổi (commit)
```sh
git commit -m "Mô tả thay đổi"
```
- **Ý nghĩa:** Lưu snapshot mã nguồn vào lịch sử dự án.
- **Thói quen tốt:** Commit nhỏ, thông điệp rõ ràng ở thì hiện tại ("Add login API").
- **Tùy chọn hữu ích:**
  ```sh
  git commit                          # Mở editor viết thông điệp nhiều dòng
  git commit --amend                  # Sửa commit gần nhất
  git commit --amend --no-edit        # Giữ nguyên message, chỉ cập nhật nội dung
  git commit --no-verify              # Bỏ qua hook (chỉ dùng khi chắc chắn)
  ```
- **Lỗi hay gặp:** `nothing to commit` → chưa add file hoặc đang ở nhánh sai.

### 4.6. Xem lịch sử commit
```sh
git log
```
- **Ý nghĩa:** Theo dõi lịch sử thay đổi, tác giả, thời gian, message.
- **Các tuỳ chọn phổ biến:**
  ```sh
  git log --oneline --graph --decorate --all    # Dạng cây tổng quan
  git log --stat --since="2 weeks"             # Thống kê file, lọc theo thời gian
  git show <hash>                               # Xem chi tiết một commit
  git show <hash>:path/to/file                  # Xem nội dung file tại commit
  ```
- **Tip:** Dùng alias `git lg` (đã khai báo ở phần 3.5) để xem nhanh.

### 4.7. Đẩy code lên remote (push)
```sh
git push origin <ten_nhanh>
```
- **Ý nghĩa:** Đồng bộ commit địa phương lên remote (GitHub, GitLab,...).
- **Khi nào dùng:** Sau khi commit xong và muốn chia sẻ/bảo vệ code.
- **Tuỳ chọn quan trọng:**
  ```sh
  git push -u origin <ten_nhanh>        # Thiết lập upstream cho nhánh mới
  git push origin main --force-with-lease  # Cập nhật sau khi rebase (an toàn hơn force)
  git push origin :ten_nhanh            # Xoá nhánh trên remote
  ```
- **Lỗi thường gặp:** "rejected - non-fast-forward" → cần `git pull --rebase` trước khi push.

### 4.8. Kéo code mới nhất về máy (pull)
```sh
git pull origin <ten_nhanh>
```
- **Ý nghĩa:** Lấy commit mới nhất về local và merge vào nhánh hiện tại.
- **So sánh:** `git pull = git fetch + git merge`.
- **Tuỳ chọn:**
  ```sh
  git pull --rebase origin main    # Giữ lịch sử commit gọn
  git pull --ff-only               # Chỉ merge nếu fast-forward được
  ```
- **Khuyến nghị:** Trước khi làm việc nên pull để tránh xung đột.

### 4.9. Làm việc với nhánh (branch)
- **Tạo nhánh mới:**
  ```sh
  git branch <ten_nhanh>
  git switch -c <ten_nhanh>   # Git >= 2.23
  ```
- **Chuyển nhánh:**
  ```sh
  git checkout <ten_nhanh>
  git switch <ten_nhanh>
  ```
- **Đổi tên nhánh hiện tại:**
  ```sh
  git branch -m <ten_moi>
  ```
- **Ghi chú:** Đặt tên nhánh mô tả rõ ràng: `feature/login`, `bugfix/payment`.

### 4.10. Xoá nhánh
- **Local:**
  ```sh
  git branch -d <ten_nhanh>   # Chỉ xoá nếu đã merge
  git branch -D <ten_nhanh>   # Xoá cưỡng bức (cẩn thận)
  ```
- **Remote:**
  ```sh
  git push origin --delete <ten_nhanh>
  ```
- **Lưu ý:** Luôn kiểm tra `git branch`/`git branch -r` trước khi xoá.

### 4.11. Hợp nhất nhánh (merge)
```sh
git checkout main
git merge <ten_nhanh>
```
- **Ý nghĩa:** Kết hợp thay đổi từ nhánh khác vào nhánh hiện tại.
- **Tuỳ chọn:**
  ```sh
  git merge --no-ff <ten_nhanh>   # Ghi lại commit merge (dễ theo dõi lịch sử)
  git merge --squash <ten_nhanh>  # Gộp nhiều commit thành một trước khi merge
  ```
- **Xử lý conflict:** Git đánh dấu `<<<<<<<`…`=======`…`>>>>>>>`. Sửa tay, rồi:
  ```sh
  git add <file_conflict>
  git commit
  ```

### 4.12. Rebase (nâng cao)
```sh
git checkout <ten_nhanh>
git rebase main
```
- **Ý nghĩa:** Đặt commit của nhánh hiện tại lên đầu nhánh mục tiêu, lịch sử thành đường thẳng.
- **Khi nên dùng:** Dọn sạch lịch sử trước khi merge, cập nhật nhánh làm việc theo main.
- **Tuỳ chọn:**
  ```sh
  git rebase --continue      # Sau khi giải quyết conflict
  git rebase --abort         # Huỷ rebase nếu gặp vấn đề
  git rebase -i HEAD~5       # Rebase tương tác (squash, reorder commit)
  ```
- **Lưu ý:** Không rebase nhánh đã public cho nhiều người dùng (tránh mất lịch sử).

### 4.13. Lấy thay đổi nhưng chưa merge (fetch)
```sh
git fetch origin
```
- **Ý nghĩa:** Tải commit mới từ remote về local mà không tự động merge.
- **Ứng dụng:** Kiểm tra sự khác biệt trước khi merge/pull, cập nhật branch list.
- **Ví dụ:**
  ```sh
  git fetch origin main
  git log origin/main --oneline  # Xem các commit mới
  ```

### 4.14. Quản lý remote
```sh
git remote -v
git remote add origin <url>
git remote set-url origin <url_moi>
```
- **Ý nghĩa:** Liệt kê, thêm, thay đổi địa chỉ remote.
- **Lưu ý:** Có thể thêm nhiều remote (ví dụ `origin`, `upstream`).

### 4.15. Hoàn tác thay đổi
- **Khôi phục file về trạng thái commit gần nhất:**
  ```sh
  git restore <file>
  git restore --staged <file>   # Bỏ staging
  ```
- **Undo commit cuối (giữ thay đổi trong staging):**
  ```sh
  git reset --soft HEAD~1
  ```
- **Undo commit và xoá thay đổi:**
  ```sh
  git reset --hard HEAD~1   # Cẩn thận, mất dữ liệu chưa commit
  ```
- **So sánh với stash:** `git stash` phù hợp khi muốn lưu tạm mà không commit.

### 4.16. Lưu tạm thay đổi (stash)
```sh
git stash push -m "WIP: Refactor user service"
git stash list
git stash pop
```
- **Ứng dụng:** Khi cần chuyển nhánh gấp mà không muốn commit dở dang.
- **Tuỳ chọn:**
  ```sh
  git stash push -u        # Bao gồm cả file chưa được track
  git stash drop stash@{1}
  ```

### 4.17. Kiểm tra ai sửa dòng nào (blame)
```sh
git blame path/to/file
```
- **Ý nghĩa:** Xác định commit, tác giả cho từng dòng.
- **Tip:** Dùng `git blame -L 10,20 file` để giới hạn dòng.

### 4.18. So sánh nhánh/commit
```sh
git diff main..feature/login
git diff --stat HEAD~1 HEAD
```
- **Mục đích:** Xem sự khác biệt giữa các nhánh/commit, phục vụ review.
- **Tuỳ chọn:** `git difftool` để mở trong công cụ đồ hoạ.

>  **Kinh nghiệm:** Kết hợp các lệnh trên linh hoạt (ví dụ `git fetch` → `git checkout` → `git merge`) sẽ giúp workflow trơn tru, hạn chế xung đột.

---

---

## 5. LÀM VIỆC VỚI GITHUB (TỪ CƠ BẢN ĐẾN NÂNG CAO)

### 5.1. Tạo repository mới trên GitHub
1. **Chuẩn bị:** Đăng nhập GitHub, xác định repo public/private.
2. **Thực hiện:** Nhấn **New repository** → nhập tên, mô tả, chọn README, .gitignore, license.
3. **Kết nối với repo local:**
   ```sh
   git remote add origin https://github.com/user/repo.git
   git push -u origin main
   ```
4. **Phân quyền:** Settings → Collaborators → Add people → nhập username/email → gửi invite.
- **Lưu ý:** Repo public ai cũng thấy, repo private cần mời thành viên.
- **Bảo mật:** Kích hoạt branch protection (Settings → Branches) để yêu cầu review, CI pass mới merge.

### 5.2. Fork & Pull Request (PR) chi tiết
- **Fork:** Sao chép repo gốc về tài khoản cá nhân, phù hợp open source hoặc khi không có quyền push trực tiếp.
- **Quy trình Fork → PR:**
  1. Fork repo gốc.
  2. Clone repo fork về máy.
  3. Tạo branch mới, code, commit.
  4. Push lên fork.
  5. Vào GitHub → Compare & pull request → mô tả chi tiết → gửi PR.
- **Pull Request:** Nơi thảo luận, review, chạy CI/CD.
  - Có thể gán reviewer, assignee, label, milestone.
  - Dùng template PR để thống nhất nội dung.
- **Mẹo:** PR nhỏ, tập trung một mục tiêu, mô tả rõ, đính kèm ảnh/video nếu có UI.

### 5.3. Issues, Projects, Discussions, Release
| Tính năng   | Công dụng chính                               | Gợi ý sử dụng |
|-------------|-----------------------------------------------|---------------|
| Issues      | Báo bug, yêu cầu tính năng, giao task         | Đặt label: bug, enhancement, help-wanted... |
| Projects    | Lập bảng Kanban, Scrum, theo dõi tiến độ      | Có thể liên kết Issue/PR, tự động cập nhật trạng thái |
| Discussions | Nơi thảo luận mở, trao đổi ý tưởng            | Thay cho chat/email, thuận tiện lưu trữ |
| Release     | Đóng gói phiên bản, phát hành artefact, tag   | Ghi changelog, đính kèm file binary |
- **Lưu ý:** Có thể bật **Issue templates** để tiêu chuẩn hóa thông tin khi báo lỗi.

### 5.4. GitHub Actions & Automation
- **GitHub Actions:** Nền tảng CI/CD tích hợp. Có thể chạy test, build, deploy, quét security.
- **Ví dụ:** `.github/workflows/ci.yml` để chạy test tự động khi mở PR.
- **Marketplace:** Hàng nghìn action có sẵn (deploy AWS, gửi Slack...).
- **Quyền & chi phí:** Repo public miễn phí, repo private giới hạn theo gói.

### 5.5. Bảo mật & quản trị
- **Branch protection rules:** Yêu cầu review, cấm force push, cấm xoá branch.
- **Secret scanning & Dependabot:** Tự động phát hiện secret, cập nhật gói.
- **Code Owners:** Quy định ai phải review khi file bị sửa.
- **Audit log (GitHub Enterprise):** Theo dõi hành động người dùng.

### 5.6. So sánh HTTPS vs SSH trên GitHub
| Tiêu chí            | HTTPS                                    | SSH                                         |
|--------------------|-------------------------------------------|---------------------------------------------|
| Xác thực           | Username + password/token                 | Cặp SSH key                                 |
| Mức độ tiện dụng   | Dễ cho người mới                          | Tiện cho lập trình viên lâu dài             |
| Bảo mật            | Tốt (với token)                           | Rất tốt (keypair)                           |
| Yêu cầu cấu hình   | Thấp                                      | Phải tạo SSH key và thêm lên GitHub         |
| Dùng ở công ty     | Có thể dùng kèm proxy                     | Cần mở port 22 hoặc dùng SSH-over-HTTPS     |

### 5.7. Báo cáo & phân tích
- **Insights → Pulse/Contributors:** Thống kê commit, PR, issue.
- **Traffic:** Theo dõi lượt view, clone repo.
- **Security → Dependabot alerts:** Cảnh báo lỗ hổng package.
- **Graphs → Network:** Xem nhánh, fork, quan hệ commit.

### 5.8. Quản lý release & phiên bản
- Đặt **tag** cho commit ổn định (`git tag v1.0.0` → push tag).
- Tạo **Release** kèm changelog, binary.
- Dùng **Semantic Versioning (SemVer)** (`MAJOR.MINOR.PATCH`).
- Kết hợp Actions để tự động tạo release sau khi merge vào main.

>  **Mẹo:** Trên GitHub, mọi thao tác đều có thể thực hiện bằng REST/GraphQL API → thuận tiện tự động hoá.

---

## 6. KẾT NỐI GITHUB VỚI GIT: SSH vs HTTPS (ĐẦY ĐỦ, CHI TIẾT)

### 6.1. Kết nối bằng SSH
#### Tác dụng
- Kết nối an toàn, không cần nhập mật khẩu mỗi lần push/pull.
- Thường dùng cho lập trình viên chuyên nghiệp hoặc làm việc nhóm lâu dài.

#### Các bước thực hiện
1. **Tạo SSH Key mới:**
   ```sh
   ssh-keygen -t ed25519 -C "email@domain.com"
   # Nếu máy không hỗ trợ ed25519:
   ssh-keygen -t rsa -b 4096 -C "email@domain.com"
   ```
   - Khi được hỏi nơi lưu key, nhấn Enter để mặc định (~/.ssh/id_ed25519).
   - Đặt passphrase nếu muốn bảo mật hơn (có thể bỏ qua).
2. **Lấy public key:**
   ```sh
   cat ~/.ssh/id_ed25519.pub
   # hoặc trên Windows:
   type %USERPROFILE%\.ssh\id_ed25519.pub
   ```
3. **Thêm key lên GitHub:**
   - Đăng nhập GitHub → Settings → SSH and GPG keys → New SSH key → Dán key vào.
4. **Kiểm tra kết nối:**
   ```sh
   ssh -T git@github.com
   ```
   - Nếu hiện "Hi username! You've successfully authenticated..." là thành công.

#### Ví dụ thực tế
```sh
ssh-keygen -t ed25519 -C "abc@gmail.com"
cat ~/.ssh/id_ed25519.pub
# Dán lên GitHub, sau đó thử:
ssh -T git@github.com
```

#### Lỗi thường gặp & cách fix
- **Permission denied (publickey):**
  - Nguyên nhân: SSH key chưa thêm lên GitHub, hoặc sai key.
  - Cách fix:
    - Kiểm tra đã copy đúng public key chưa.
    - Đảm bảo dùng đúng tài khoản GitHub.
    - Kiểm tra agent SSH:
      ```sh
      eval $(ssh-agent -s)
      ssh-add ~/.ssh/id_ed25519
      ```
- **Host key verification failed:**
  - Xoá file `known_hosts` hoặc dòng liên quan trong `~/.ssh/known_hosts` rồi thử lại.

#### Lưu ý
- Mỗi máy nên tạo một SSH key riêng.
- Có thể thêm nhiều key vào một tài khoản GitHub.

#### Kiểm tra và tinh chỉnh
- Kiểm tra key đang được agent nạp:
  ```sh
  ssh-add -l
  ```
- Cấu hình `~/.ssh/config` để rút gọn:
  ```
  Host github
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519
  ```
  → Sau đó có thể `git clone github:user/repo.git`.
- Nếu dùng nhiều tài khoản GitHub, tạo nhiều cặp key và cấu hình tương ứng.

#### Sự cố nâng cao & cách xử lý
- **SSH timeout hoặc bị chặn port 22:** Dùng SSH over HTTPS:
  ```sh
  ssh -T -p 443 git@ssh.github.com
  ```
  và chỉnh `HostName ssh.github.com`, `Port 443` trong `~/.ssh/config`.
- **Xác thực 2 bước (2FA):** Không ảnh hưởng SSH, nhưng cần token cho HTTPS.

---

### 6.2. Kết nối bằng HTTPS
#### Tác dụng
- Đơn giản, không cần cấu hình SSH.
- Phù hợp cho người mới, thao tác nhanh, máy không cố định.

#### Các bước thực hiện
1. **Clone/push/pull bằng HTTPS:**
   - Khi push/pull sẽ hỏi username/password hoặc token.
2. **Tạo Personal Access Token (PAT):**
   - Vào https://github.com/settings/tokens → Generate new token → Chọn quyền → Copy token.
   - Dùng token thay cho password khi push/pull.

#### Ví dụ thực tế
```sh
git clone https://github.com/username/repo.git
# Khi push sẽ hỏi user và token
```

#### Lỗi thường gặp & cách fix
- **Authentication failed:**
  - Nguyên nhân: Sai user, sai mật khẩu, token hết hạn hoặc thiếu quyền.
  - Cách fix:
    - Tạo lại token mới, đảm bảo chọn đủ quyền (repo, workflow,...).
    - Copy đúng token, không copy thừa/ký tự trắng.
- **Support for password authentication was removed:**
  - GitHub không hỗ trợ password, bắt buộc dùng token.

#### Lưu ý
- Không chia sẻ token cho người khác.
- Có thể lưu token vào credential manager để không phải nhập lại.

#### Xử lý sự cố phổ biến
- **Lỗi SSL certificate problem:**
  - Cập nhật CA trên hệ điều hành.
  - Với Windows: `git config --global http.sslBackend schannel` để dùng chứng chỉ của Windows.
- **Proxy chặn kết nối:** Cấu hình biến môi trường `HTTPS_PROXY`, `HTTP_PROXY` hoặc dùng `git config --global http.proxy`.
- **Token hết hạn:** Regenerate, cập nhật credential manager (`git credential-manager delete https://github.com`).

### 6.3. Bảng so sánh nâng cao SSH vs HTTPS vs PAT
| Tiêu chí                         | SSH                                        | HTTPS + mật khẩu (không còn hỗ trợ) | HTTPS + PAT (Personal Access Token) |
|---------------------------------|--------------------------------------------|-------------------------------------|-------------------------------------|
| Trạng thái hỗ trợ               | Đầy đủ                                     | Ngừng từ 13/8/2021                  | Đầy đủ                               |
| Quản lý danh tính              | Keypair lưu cục bộ                         | Username/password                   | Token do người dùng tạo             |
| Độ tiện lợi dài hạn             | Rất cao, không nhập lại mỗi lần            | Không áp dụng                       | Trung bình (cần token hoặc credential helper) |
| Bảo mật                         | Cao (RSA/Ed25519)                          | Yếu                                 | Cao (có thể giới hạn scope & thời gian) |
| Setup ban đầu                   | Cần tạo & upload key, cấu hình agent       | Không áp dụng                       | Tạo token, lưu vào credential       |
| Sử dụng qua proxy nội bộ        | Cần cấu hình thêm                          | Dễ (nếu proxy cho HTTPS)            | Dễ                                   |
| Khả năng tự động hóa            | Cao (script, server CI)                    | Không áp dụng                       | Cao, nhưng phải bảo vệ token        |

>  **Khuyến nghị:** Dự án dài hạn nên dùng SSH; với môi trường bị hạn chế port, dùng HTTPS + PAT và credential helper.

---

## 7. LỖI THƯỜNG GẶP & CÁCH KHẮC PHỤC (PHÂN TÍCH SÂU)

### 7.1. `fatal: not a git repository`
- **Nguyên nhân chính:**
  - Chưa khởi tạo git (`git init`).
  - Đang ở thư mục con không chứa `.git`.
- **Khắc phục:**
  ```sh
  git init             # Tạo repo mới
  cd ..                # Quay về thư mục cha nếu vào nhầm
  ```
- **Phòng tránh:** Luôn kiểm tra `git status` để chắc chắn đang ở repo đúng.

### 7.2. `fatal: refusing to merge unrelated histories`
- **Nguyên nhân:** Hai nhánh không cùng lịch sử (ví dụ tạo repo local rồi push lên repo đã có commit).
- **Giải pháp:**
  ```sh
  git pull origin main --allow-unrelated-histories
  ```
- Sau khi merge thành công, dọn dẹp commit và cấu trúc lại repo cho thống nhất.

### 7.3. `failed to push some refs to ...`
- **Nguyên nhân:** Remote có commit mới, local chưa cập nhật.
- **Khắc phục:**
  ```sh
  git pull --rebase origin main
  git push origin main
  ```
- **Trường hợp rebase gây lỗi:** Dùng `git pull --rebase --autostash` để tự stash thay đổi local.

### 7.4. Merge conflict
- **Nguyên nhân:** Hai nhánh chỉnh sửa cùng phần của file.
- **Cách xử lý:**
  1. Mở file có marker `<<<<<<<`, `=======`, `>>>>>>>`.
  2. Chọn hoặc kết hợp đoạn code phù hợp.
  3. Lưu file, rồi:
     ```sh
     git add <file>
     git commit
     ```
- **Công cụ hỗ trợ:** VSCode merge tool, GitKraken, `git mergetool`.
- **Phòng tránh:** Pull/update branch thường xuyên, chia nhỏ PR.

### 7.5. `Permission denied (publickey)`
- **Nguyên nhân:** SSH key chưa thêm hoặc sai key.
- **Khắc phục:**
  - Tạo key mới (`ssh-keygen`) và thêm lên GitHub.
  - Đảm bảo agent đã nạp key: `ssh-add ~/.ssh/id_ed25519`.
- **Lưu ý:** Nếu dùng nhiều key, cấu hình `~/.ssh/config` rõ ràng.

### 7.6. `error: Your branch is ahead/behind ...`
- **Nguyên nhân:** Lịch sử local và remote lệch nhau.
- **Khắc phục:**
  ```sh
  git pull --rebase
  # hoặc nếu muốn bỏ thay đổi local:
  git reset --hard origin/main
  ```
- **Tip:** `git status -sb` sẽ thông báo rõ bạn ahead/behind bao nhiêu commit.

### 7.7. `error: failed to merge`
- **Nguyên nhân:** Merge/rebase gặp conflict chưa giải quyết.
- **Khắc phục:**
  - Sửa conflict, `git add`, rồi `git merge --continue` hoặc `git rebase --continue`.
  - Huỷ thao tác: `git merge --abort` hoặc `git rebase --abort`.

### 7.8. `Detached HEAD`
- **Nguyên nhân:** Checkout trực tiếp commit thay vì branch.
- **Fix:**
  ```sh
  git checkout main      # Quay về branch
  # Nếu muốn tạo branch mới từ commit hiện tại:
  git checkout -b hotfix
  ```
- **Lưu ý:** Trong trạng thái detached, mọi commit mới dễ bị mất nếu không tạo nhánh.

### 7.9. `fatal: could not read Username for 'https://github.com': terminal prompts disabled`
- **Nguyên nhân:** Dùng HTTPS trong môi trường không cho nhập (CI/CD) hoặc thiếu credential helper.
- **Khắc phục:**
  - Thiết lập credential helper.
  - Dùng token qua biến môi trường: `git clone https://<token>@github.com/user/repo.git`.
  - Đối với CI, dùng SSH key hoặc `actions/checkout` (GitHub Actions).

### 7.10. `fatal: the remote end hung up unexpectedly`
- **Nguyên nhân:** Kết nối mạng kém, proxy, repo lớn, Git packfile quá lớn.
- **Cách khắc phục:**
  - Thiết lập `git config --global http.postBuffer 524288000` (500MB).
  - Kiểm tra kết nối mạng, proxy.
  - Chia nhỏ commit, giảm kích thước file (dùng Git LFS cho file lớn).

### 7.11. Lỗi liên quan `.gitignore`
- **Vấn đề:** File đã commit rồi mới thêm vào `.gitignore`.
- **Giải pháp:**
  ```sh
  git rm --cached <file>
  git commit -m "Remove tracked file"
  ```
- **Nhớ:** `.gitignore` chỉ áp dụng cho file chưa được track.

### 7.12. Công cụ hỗ trợ tìm lỗi
- `git fsck`: Kiểm tra tính toàn vẹn repo.
- `git reflog`: Phục hồi commit/branch lỡ xoá.
- `git bisect`: Tìm commit gây bug bằng binary search.

### 7.13. Lỗi liên quan Git LFS
- **Triệu chứng:** Không push được file lớn, báo "This exceeds GitHub's file size limit"
- **Khắc phục:**
  ```sh
  git lfs install
  git lfs track "*.psd"
  git add .gitattributes
  git add file.psd
  git commit
  git push
  ```
- **Lưu ý:** Git LFS yêu cầu cài plugin, chú ý quota dung lượng.

### 7.14. Vấn đề với submodule
- **Triệu chứng:** Submodule không cập nhật khi clone hoặc pull.
- **Khắc phục:**
  ```sh
  git submodule init
  git submodule update
  git submodule update --remote --merge   # Lấy phiên bản mới nhất của submodule
  ```
- **Mẹo:** Dùng `git clone --recurse-submodules` để tự động lấy submodule ngay từ đầu.

### 7.15. Credential cache lỗi thời
- **Triệu chứng:** Git liên tục yêu cầu đăng nhập dù đã lưu credential.
- **Khắc phục:**
  - Xoá credential cũ: `git credential-manager delete https://github.com`
  - Thiết lập lại helper: `git config --global credential.helper manager-core`
  - Với macOS: dùng `Keychain Access` xoá mục GitHub.

>  **Nguyên tắc vàng:** Đọc kỹ thông báo lỗi, copy nguyên văn tìm trên Google/StackOverflow, đa số đã có lời giải. Đừng ngại tạo Issue/Discussion hoặc hỏi team.

---

## 8. LÀM VIỆC NHÓM VỚI GIT & GITHUB (TEAMWORK CHUYÊN NGHIỆP)

### 8.1. Tạo dự án nhóm trên GitHub
1. **Một thành viên tạo repository trên GitHub** (nên là leader hoặc người quản lý):
   - Nhấn **New repository** → Đặt tên → Tích chọn "Add a README" → Tạo repo.
2. **Thêm thành viên vào repo:**
   - Vào repo → Settings → Collaborators → Add people → Nhập email/tên GitHub → Gửi invite.
   - Thành viên nhận email và accept.

### 8.2. Các mô hình quản lý nhóm phổ biến (phân tích)

| Mô hình                    | Mô tả ngắn                                              | Ưu điểm                                      | Nhược điểm                                | Khi nên dùng                             |
|---------------------------|----------------------------------------------------------|----------------------------------------------|-------------------------------------------|------------------------------------------|
| Shared Repository         | Tất cả thành viên push trực tiếp vào repo chung         | Đơn giản, nhanh, dễ thiết lập                | Dễ xung đột, khó kiểm soát chất lượng     | Nhóm nhỏ, tin tưởng nhau                 |
| Fork & Pull Request       | Mỗi người fork, làm việc trên repo riêng, gửi PR         | Kiểm soát tốt, phù hợp open source           | Quy trình dài hơn, cần review kỹ          | Dự án open source, nhiều người đóng góp |
| Gitflow Workflow          | Có nhánh main, develop, feature, release, hotfix         | Quản lý phiên bản chặt, rõ vai trò nhánh     | Cấu trúc phức tạp, nhiều branch           | Dự án lớn, phát hành định kỳ             |
| Trunk-based Development   | Mọi người commit vào main/trunk, feature flag            | Phát hành nhanh, CI/CD mạnh                  | Yêu cầu kiểm thử tự động, kỷ luật cao     | Startup, sản phẩm deploy liên tục        |
| MonoRepo                  | Nhiều dự án chung 1 repo                                 | Dễ chia sẻ code, đồng bộ version             | Repo lớn, cần tooling hỗ trợ              | Doanh nghiệp lớn, nhiều module liên quan |

#### Phân tích Gitflow (ví dụ)
- **Nhánh chính:** `main` (production), `develop` (tích hợp), `feature/*`, `release/*`, `hotfix/*`.
- **Quy trình cơ bản:**
  1. Tạo `feature/login` từ `develop`.
  2. Code, commit, PR → merge vào `develop`.
  3. Khi sắp release, tạo `release/1.0` từ `develop`, fix bug, merge vào `main` & `develop`.
  4. Nếu có lỗi production, tạo `hotfix/1.0.1` từ `main`, fix xong merge ngược lại.
- **Ưu điểm:** Quản lý release rõ ràng.
- **Nhược:** Nhiều branch phải đồng bộ → cần kỷ luật.

```mermaid
flowchart LR
    A[main] -->|tạo| B[develop]
    B -->|feature| C(feature/login)
    C -->|merge| B
    B -->|chuẩn bị phát hành| D(release/1.0)
    D -->|merge production| A
    D -->|merge ngược| B
    A -->|khẩn cấp| E(hotfix/1.0.1)
    E -->|merge production| A
    E -->|merge develop| B
```

#### Phân tích Trunk-based Development
- **Nguyên tắc:** Mọi người commit vào `main`/`trunk` (có thể qua PR), branch tồn tại rất ngắn (dưới 1-2 ngày).
- **Bảo đảm:** CI/CD mạnh, feature flag để bật/tắt tính năng chưa hoàn thiện.
- **Ưu điểm:** Triển khai liên tục, giảm merge phức tạp.
- **Thách thức:** Yêu cầu tự động hoá test, review nhanh, giao tiếp tốt.

### 8.3. Quy trình teamwork chuẩn (gợi ý từng bước)
1. **Lên kế hoạch:** Tạo Issue/Task trong Project board, gán người thực hiện.
2. **Tạo branch riêng:**
   ```sh
   git checkout -b feature/login
   ```
3. **Phát triển & commit:** Commit nhỏ, rõ message, đính kèm Issue ID (`feat: add login #123`).
4. **Push & tạo PR:**
   ```sh
   git push origin feature/login
   ```
   - Mô tả rõ nội dung, ảnh minh họa, checklist test.
5. **Code review & CI:** Reviewer comment, chạy GitHub Actions kiểm tra tự động.
6. **Fix comment & merge:** Sửa theo review, rebase/merge main, giải quyết conflict.
7. **Deploy & theo dõi:** Tag release, cập nhật changelog, monitor sau deploy.

### 8.4. Vai trò trong team Git
- **Maintainer/Tech Lead:** Duyệt PR, định hướng kiến trúc, thiết lập quy tắc.
- **Reviewer:** Kiểm tra code, yêu cầu chỉnh sửa, đảm bảo chất lượng.
- **Contributor:** Phát triển tính năng, tuân thủ quy trình.
- **DevOps/CI Engineer:** Quản lý pipeline, môi trường build/deploy.
- **Product/Project Manager:** Tạo task, theo dõi tiến độ qua Issues/Projects.

### 8.5. Bộ lệnh teamwork thường dùng
- Cập nhật branch theo main:
  ```sh
  git checkout feature/login
  git fetch origin
  git rebase origin/main
  ```
- Đồng bộ fork với repo gốc:
  ```sh
  git remote add upstream https://github.com/org/repo.git
  git fetch upstream
  git rebase upstream/main
  ```
- Kiểm tra PR trước khi merge:
  ```sh
  git fetch origin pull/123/head:pr-123
  git checkout pr-123
  ```

### 8.6. Sử dụng Issue, Project, Release hiệu quả
- **Issue template:** Chuẩn hoá nội dung bug report/feature request.
- **Labels:** Phân loại (bug, feature, urgent...), kết hợp automation.
- **Project board:** Chia cột (Todo, In progress, Review, Done), gán người, deadline.
- **Milestones:** Gom các issue/PR cho một phiên bản cụ thể.
- **Release note:** Ghi rõ tính năng, bug fix, breaking change.

### 8.7. Giao tiếp & review code
- Dùng comment trên PR, mention `@username` để trao đổi.
- Ghi nhận kết quả test, ảnh chụp, video nếu là UI.
- Sử dụng chế độ "Suggest changes" để contributor áp dụng nhanh.
- Đặt SLA review (ví dụ 24h) để PR không tồn đọng.

### 8.8. Kiểm soát chất lượng
- **CI/CD:** Chạy lint, unit test, integration test tự động.
- **Branch protection:** Yêu cầu số lượng reviewer tối thiểu, cấm merge khi CI fail.
- **Security:** Quét secret, dependency, bật security policy.
- **Code style:** Sử dụng formatter, linter, pre-commit hook.

### 8.9. Mẹo & tài liệu nội bộ
- Tạo file `CONTRIBUTING.md` hướng dẫn chi tiết quy trình đóng góp.
- Ghi lại best practice vào wiki nội bộ.
- Đào tạo định kỳ về Git/GitHub cho thành viên mới.
- Dùng Slack/Teams tích hợp GitHub (thông báo PR, build, deploy).

>  **Chìa khóa teamwork:** Giao tiếp rõ ràng, quy trình thống nhất, tự động hoá kiểm thử, review nghiêm túc và cập nhật liên tục.

---

## 9. LỆNH NÂNG CAO, MẸO & CÔNG CỤ HỖ TRỢ (PHÂN TÍCH)

### 9.1. Lệnh nâng cao (theo nhóm chức năng)
- **Quản lý branch/remote:**
  ```sh
  git branch -av                 # Liệt kê branch local & remote
  git remote show origin         # Thông tin chi tiết về remote
  git remote prune origin        # Dọn nhánh remote đã xoá
  ```
- **Thao tác với commit:**
  ```sh
  git cherry-pick <hash>         # Lấy commit bất kỳ áp dụng vào branch hiện tại
  git revert <hash>              # Tạo commit đảo ngược
  git rebase -i HEAD~5           # Rebase tương tác, gộp/sắp xếp commit
  git reflog                     # Xem lịch sử HEAD, cứu commit lỡ xoá
  ```
- **Tìm kiếm & so sánh:**
  ```sh
  git grep "TODO"                # Tìm chuỗi trong repo
  git blame file.dart            # Ai sửa dòng nào
  git bisect start               # Tìm commit gây bug bằng binary search
  ```
- **Tối ưu repo:**
  ```sh
  git gc --prune=now --aggressive   # Dọn dẹp và tối ưu repo
  git lfs install                    # Sử dụng Git LFS cho file lớn
  ```
- **Phục hồi & cứu nguy:**
  ```sh
  git stash list                    # Danh sách stash
  git stash apply stash@{2}         # Áp dụng stash cụ thể
  git fsck                          # Kiểm tra toàn vẹn dữ liệu
  ```

### 9.2. Công cụ hỗ trợ & tích hợp
- **Git GUI:** GitHub Desktop, Sourcetree, GitKraken, Tower (macOS).
- **IDE/Editor:** VSCode (GitLens, Git Graph), JetBrains IDE, Visual Studio.
- **Terminal:** Windows Terminal, iTerm2, oh-my-zsh với plugin git.
- **Quản lý secret:** GitGuardian, GitLeaks, GitHub secret scanning.
- **CI/CD:** GitHub Actions, Jenkins, GitLab CI, CircleCI.
- **Code review:** Reviewable, Phabricator, Gerrit (cho dự án lớn).

### 9.3. Tips bảo mật & best practice
- Không push file chứa mật khẩu, token; dùng `.gitignore` và secret manager.
- Kích hoạt 2FA cho tài khoản GitHub, sử dụng SSH key an toàn.
- Thiết lập branch protection, require review, require status checks.
- Sử dụng Dependabot để cập nhật dependency, quét lỗ hổng tự động.
- Lưu trữ backup repo (mirror) nếu dự án quan trọng.

### 9.4. Tự động hoá & hook
- **Git hooks:** `pre-commit`, `pre-push`, `commit-msg` để chạy lint/test.
- **Husky (JavaScript):** Tích hợp hook dễ dàng.
- **Custom script:** Tạo alias/hàm shell để tự động hóa (ví dụ deploy, release).
- **GitHub CLI (`gh`):** Quản lý issue, PR, release ngay từ terminal.

### 9.5. Bảng tổng hợp lệnh Git tiêu biểu
| Nhóm thao tác           | Mục đích                                | Lệnh chính                                | Ví dụ thực tế |
|-------------------------|-----------------------------------------|-------------------------------------------|---------------|
| Khởi tạo                | Tạo repo mới                            | `git init`, `git clone`                   | `git clone git@github.com:org/app.git` |
| Theo dõi thay đổi       | Kiểm tra trạng thái, diff               | `git status`, `git diff`, `git log`       | `git log --oneline --graph` |
| Staging & commit        | Chuẩn bị và lưu snapshot                | `git add`, `git commit`, `git commit --amend` | `git add -p src/*.dart` |
| Branch & merge          | Phát triển song song, hợp nhất          | `git branch`, `git switch`, `git merge`   | `git merge --no-ff feature/login` |
| Rebase & cherry-pick    | Làm gọn lịch sử, áp dụng commit chọn lọc| `git rebase`, `git rebase -i`, `git cherry-pick` | `git cherry-pick abc1234` |
| Đồng bộ remote          | Đẩy/kéo code, quản lý remote            | `git fetch`, `git pull`, `git push`, `git remote` | `git push -u origin feature/api` |
| Hoàn tác & phục hồi     | Khôi phục, reset, stash                 | `git restore`, `git reset`, `git stash`, `git reflog` | `git reset --hard HEAD~1` |
| Kiểm tra & tối ưu       | Kiểm thử repo, tìm kiếm, tối ưu         | `git grep`, `git fsck`, `git gc`, `git lfs` | `git grep "TODO" lib/` |
| Phát hành               | Tag, release                            | `git tag`, `git describe`                 | `git tag v2.0.0 && git push origin v2.0.0` |

>  **Gợi ý:** In bảng này và dán cạnh bàn làm việc hoặc lưu dưới dạng cheat sheet để tra cứu nhanh.

## 10. TÀI NGUYÊN THAM KHẢO & LỘ TRÌNH HỌC

### 10.1. Tài liệu chính thống
- [Tài liệu Git chính thức](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com/)
- [Pro Git Book (Có tiếng Việt)](https://git-scm.com/book/en/v2) – sách toàn diện.

### 10.2. Học qua thực hành
- [learngitbranching.js.org](https://learngitbranching.js.org/) – thực hành branch trực quan.
- [Git-it](https://github.com/jlord/git-it-electron) – ứng dụng desktop học Git.
- [Katacoda Git Scenarios](https://www.katacoda.com/courses/git) – kịch bản tương tác.

### 10.3. Cheat sheet & blog hữu ích
- [Git Cheat Sheet (GitHub Education)](https://education.github.com/git-cheat-sheet-education.pdf)
- [Oh Shit, Git!?!](https://ohshitgit.com/) – hướng dẫn xử lý sự cố nhanh.
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials) – bài viết chi tiết.
- [Git Tower Blog](https://www.git-tower.com/learn/git/faq) – FAQ Git nâng cao.

### 10.4. Lộ trình nâng cao
1. **Cơ bản:** Hiểu commit, branch, merge, remote.
2. **Trung cấp:** Rebase, cherry-pick, stash, conflict resolution.
3. **Nâng cao:** Git internals, hook, submodule, LFS, workflows nâng cao.
4. **Team & DevOps:** CI/CD, release management, security, analytics.

>  **Gợi ý:** Lưu bookmark các tài liệu quan trọng, tạo wiki nội bộ để chia sẻ kiến thức cho team.

### 10.5. Tổng kết & thực hành
- Luyện tập với repo demo, cố tình tạo lỗi để học cách xử lý.
- Tham gia dự án open source nhỏ để trải nghiệm workflow thực tế.
- Theo dõi blog của GitHub, GitLab, Atlassian để cập nhật tính năng mới.

## 11. KẾT LUẬN & GỢI Ý DUY TRÌ
- Git/GitHub là xương sống của phát triển phần mềm hiện đại. Thành thạo Git giúp bạn làm việc tự tin, hiệu quả và chuyên nghiệp.
- Duy trì thói quen commit nhỏ, push thường xuyên, review kỹ lưỡng, bảo mật nghiêm ngặt.
- Liên tục học hỏi, cập nhật workflow mới, áp dụng tự động hoá để tiết kiệm thời gian.
- Ghi nhớ: **Hiểu bản chất Git giúp bạn xử lý mọi tình huống bình tĩnh và chính xác.**

---

Nếu gặp lỗi, hãy copy thông báo lỗi và tìm kiếm trên Google hoặc StackOverflow. Luôn commit nhỏ, ghi chú rõ ràng, push code thường xuyên để tránh mất dữ liệu. Đừng ngại hỏi đồng đội hoặc cộng đồng khi cần hỗ trợ.

## 12. GIẤY PHÉP
```sh
MIT License

Copyright (c) 2025 Nguyễn Văn Trọng

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
