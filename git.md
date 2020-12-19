[!Back to main](./git).
- Thiết lập chứng thực cá nhân

```
   $ git config --global user.name "User Name"
   $ git config --global user.email "username@gmail.com"
```

  - Lưu ý: --global được sử dụng để áp dụng cho tất cả các projects. Nếu bạn ko sử dụng --global thì settings sẽ chỉ dùng cho riêng project đó.
- Tạo một kho chứa Git

  ```
  $ git init
  ```

  - Nếu như bạn muốn theo dõi một dự án cũ trong Git, bạn cần ở trong thư mục của dự án đó. Lệnh này sẽ tạo một thư mục mới có tên .git, thư mục này chứa tất cả các tập tin cần thiết cho kho chứa.
- Sao chép một kho chứa đã tồn tại

  ```
  $ git clone https://github.com/user/repository.git
  
  ```
  - Câu lệnh trên sẽ tạo một thư mục mới có tên giống trên của repo.
- Nhánh trong git
Khi sử dụng Git, bạn có thể tạo ra nhiều nhánh (branch) khác nhau. Câu lệnh Git này dùng để kiểm tra branch hiện tại:
  
  ```
  $ git branch
  ```
  
- Để tạo mới một branch:
  
  ```
  $ git branch <name_branch>
  ```
  
- Để chuyển và tạo mới:
  
  ```
  $ git branch -b <name_branch>
  ```
  
- Chuyển nhánh
  - Trước khi muốn thay đổi source code, điều đầu tiên mà bạn cần phải làm là checkout một nhánh. Để checkout một nhánh, bạn dùng câu lệnh Git sau:
  
  ```
  $ git checkout <name_branch>
  ```
  
- Cập nhật thay đổi
  - Sau khi bạn thay đổi source code: thêm mới, sửa, xoá files,… Bạn cần phải cập nhật lên Staging Area. Để cập nhật hết các files:
  
  ```
   git add .
  ```
  
- Sau lệnh add, bạn cần sử dụng câu lệnh Commit để đây thông tin thay đổi lên Local Respository:
  
  ```
   git commit -m "Message"
  ```
  
- Cập nhật lên server
  - Sau câu lệnh Commit, thông tin mới chỉ được cập nhật lên Local Repository. Nếu muốn cập nhật lên server thì bạn phải sử dụng câu lệnh push:
  
  ```
   git push origin <name_branch>
  ```
  
- Ngoài ra, nếu chưa tồn tại remote trên server thì bạn cần phải add mới một remote trước rồi mới push:
  
  ```
   git remote add origin <remote_url>
  ```
  
  
  ```
   git push origin <name_branch>
  ```
  
- Gộp nhánh
  -Sau một thời gian cập nhật các file và push lên git trên branch mới, bây giờ mình cần ghép (merge) code lại vào nhánh gốc (master). Trước tiên, cần phải checkout ra khỏi branch hiện tại cần gộp để vào branch master, sau đó thì dùng lệnh merge để ghép branch mới vào master:
  
  ```
   git checkout master
  ```
  
  
  ```
   git merge <new_branch>
  ```
  
- Xem lại lịch sử commit
  
  ```
   git log
  ```
  
  - Lệnh git log sẽ cho bạn biết về người commit, ngày giờ, message của những lần commit đó.
- Xem thay đổi trước khi push
  
  ```
   git diff
  ```
  
  - Lệnh này giúp bạn biết những gì đã được thay đổi giữa nhánh hiện tại và nhánh trước nó.
- Gộp commit
  
  ```
   git rebase -i HEAD~
  ```
  
  - Sau dấu ~ là số commit bạn muốn gộp. Sau khi gõ lệnh này một cửa sổ trình soạn thảo hiện ra. Thay đổi ký tự pick của dòng các dòng sau dòng đầu thành s rồi lưu lại/kết thúc. Khi đó, trình soạn thảo để chỉnh sửa giải thích commit thiết lập cho commit sau khi đã tổng hợp sẽ được hiển thị, nên hãy chỉnh sửa lưu lại/kết thúc.
- Pull từ remote repository
  
  ```
   git pull origin master
  ```
  
  - Lệnh trên sẽ gộp những thay đổi mới kéo về từ máy chủ từ xa với nhánh hiện tại trên máy local.

