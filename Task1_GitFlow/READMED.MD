# Git - Github
- Git là một hệ thống quản lý mã nguồn phân tán (Distributed Version Control System - DVCS) được phát triển bởi Linus Torvalds, người cũng là tác giả của hệ điều hành Linux. Git được sử dụng rộng rãi trong phát triển phần mềm để quản lý và theo dõi các phiên bản của mã nguồn.

- Một số đặc điểm quan trọng của Git bao gồm:

1. Phân tán: Git cho phép nhiều người làm việc trên cùng một dự án mà không cần phải kết nối liên tục với máy chủ trung tâm. Mỗi người có bản sao đầy đủ của toàn bộ kho lưu trữ trên máy tính của họ.

2. Lịch sử mã nguồn: Git theo dõi toàn bộ lịch sử thay đổi của mã nguồn. Mỗi lần thay đổi được ghi lại dưới dạng commit, và bạn có thể quay lại bất kỳ phiên bản trước đó.

3. Branching và merging: Git cho phép bạn tạo và quản lý các nhánh (branches) riêng biệt để phát triển tính năng mới hoặc sửa lỗi mà không ảnh hưởng đến phiên bản ổn định của mã nguồn. Sau đó, bạn có thể merge (kết hợp) các thay đổi từ branch phụ vào branch chính.

4. Hiệu suất nhanh: Git được thiết kế để hoạt động nhanh chóng, thậm chí trên các dự án lớn với hàng nghìn tệp và hàng triệu dòng mã nguồn.

5. Cộng tác nhóm: Git hỗ trợ công việc cộng tác của nhiều người trong việc phát triển phần mềm. Nó cho phép bạn chia sẻ mã nguồn, quản lý xung đột (conflicts), và theo dõi công việc của từng thành viên trong dự án.

6. Git là một công cụ quan trọng trong phát triển phần mềm và quản lý mã nguồn. Nó được sử dụng rộng rãi trong cộng đồng phát triển phần mềm mở và trong nhiều dự án thương mại.
# Pull changes
- Trong Git, để kéo (pull) các thay đổi từ kho lưu trữ từ xa (remote repository) và cập nhật phiên bản của bạn với phiên bản mới nhất trên remote repository, sử dụng lệnh ```git pull```. 
# Branches
- Trong Git, branches (nhánh) là một khía cạnh quan trọng của quản lý lịch sử mã nguồn và phát triển dự án. Branches cho phép bạn làm việc trên nhiều phiên bản của dự án cùng một lúc, thực hiện thay đổi và phát triển mà không ảnh hưởng đến các phiên bản chính
 ### Một số câu lệnh khi làm việc với brach:
1. Tạo branch mới: Để tạo một branch mới:
    ```
    // git branch branch-name
    git branch feature-branch
    ```
2. Chuyển sang một branch khác (checkout):
   ```
   //  git checkout branch-name
   git checkout feature-
   // or với phiên bản mới
   git switch feature-branch

   ```
3. Tạo và chuyển sang branch mới cùng một lúc:
    ```
    git checkout -b new-feature-branch
    ```
4. Xem danh sách các branches: 
    ```
    git branch
    ```
5. Xóa branch: Để xóa một branch sau khi bạn đã hoàn thành công việc trên nó
    ```
    //git branch -d branch-name
    git branch -d feature-
    // Để xóa branch mà không cần xác nhận, bạn có thể sử dụng -D:
    git branch -D feature-branch

    ```
6. Merge branch: Để kết hợp (merge) các thay đổi từ một branch vào branch khác
    ```
    // git merge
    git merge feature-branch

    ```
7. Push branch lên kho lưu trữ từ xa: Nếu bạn làm việc với kho lưu trữ từ xa như GitHub, để đưa branch lên remote repository
    ```
    git push origin feature-branch

    ```
8. Lấy thông tin về remote branches:
    ```
    git branch

    ```
9. Đặt branch hiện tại cho commit cụ thể: Để di chuyển branch hiện tại đến một commit cụ thể: 
    ```
    git reset commit-hash

    ```
# Gitignore file
- Là một tệp tin cấu hình trong một kho lưu trữ Git (Git repository) được sử dụng để chỉ định các tệp và thư mục mà Git nên bỏ qua (ignore) khi theo dõi thay đổi trong kho lưu trữ. Điều này giúp loại bỏ các tệp và thư mục không cần thiết khỏi lịch sử Git và khỏi quá trình đặt các thay đổi dưới sự theo dõi của Git.
- Tệp tin .gitignore thường chứa các mẫu (patterns) để chỉ định tệp hoặc thư mục mà bạn muốn bỏ qua
- Để bỏ qua một tệp cụ thể thêm dòng sau vào .gitignore:
```
filename.txt
```
- Để bỏ qua tất cả các tệp có một phần mở rộng cụ thể, bạn có thể sử dụng dấu *. Ví dụ, để bỏ qua tất cả các tệp .log, 
```
*.log
```
- Để bỏ qua một thư mục cụ thể :
```
directory/
```
- Để bỏ qua tất cả các tệp hoặc thư mục bên trong một thư mục cụ thể, bạn có thể sử dụng dấu **. Ví dụ, để bỏ qua tất cả các tệp và thư mục bên trong node: 
```
node_modules/**
```
# Git flow
![Alt text](git-flow.png)
- Tạo nhánh chính master: không sửa lỗi code trên nhánh này 
- Tạo nhánh developer song song với nhánh master để hợp nhất các nhánh khác  
- Phát triển tính năng
  - Tạo các nhánh tính năng (future branches).
  - Các nhánh tính năng hoàn thành thì merge lại nhánh developer
  - Nhánh developer đây lên nhánh release
  - Nhánh release sẽ đẩy lênn nhanh master
  - Nhánh master đẩy lên production
  - Xóa release version
  - Lặp lại để phát triển các tính năng khác.
- Sửa lỗi
  - Đẩy lỗi về nhánh hotfixes
  - Dưa về nhánh developer
  - Sau đó sẽ tương tự như phát triển tính năng 
  - Nếu lỗi nhỏ và xử lý nhanh thi từ hotfiexs đâyr lại master và đẩy lên production

```git
- Tao repo cho dự án
create repo in github
create file, folder, project (README.md)
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://xxx.git
git push -u origin main
- Tạo nhánh develop
git branch develop
git branch
git push -u origin develop
- Leader giao nhiệm vụ cho developer (issues in github #1)
- Tạo nhánh tính năng và sửa code 
git checkout -b feature/1-add-cart.model-file devolop
code các chức năng theo yêu cầu
git add 
git status
git commit -m "#1 - anhdev update cart model"
git push
Note: #1 là số thứ tự của nhiệm vụ, commit message phải có #1 - để reference commit vào task tương ứng trong issua github
- Pull lên nhanh develop - github (nho reference #1)
- Leader xem xét, nếu code ok thì sẽ merge lên develop
- Xóa future 1 branch
git branch -d feature/1-add-cart.model-file (xóa local)
git push origin -d feature/1-add-cart.model-file (xóa github)
- đẩy từ nhánh develop lên release
git checkout develop
git pull
git checkout -b release-1.0.0
git add / status
git commit -m 'publish release v1.0.0'
git tag 'v1.0.0'
git push
git merge develop
git push -u origin release-1.0.0
- Leader merge nhanh release-1.0.0 lên nhánh main, sau đó đẩy lên production
git checkout main
git pull
git tag 'v1.0.0'
git push --tags 
- tạo tag và đẩy lên tag lên github
git tag 'v1.0.0'
git push --tags
- Xoá release branch
git branch
git branch -d release-1.0.0 (xóa local)
git push origin -d release-1.0.0 (xóa github)

```