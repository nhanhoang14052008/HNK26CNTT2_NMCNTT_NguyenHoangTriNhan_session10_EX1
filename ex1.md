# Phần 1. Phân tích tình huống của Nam

## 1. Những sai lầm trong tư duy

Sai lầm 1: Dùng Word (.docx) để lưu trữ tài liệu dự án trên GitHub.

-   `.docx` là định dạng Rich Text, chứa nội dung cùng thông tin định dạng và cấu trúc dữ liệu bên trong.
    
-   GitHub khó hiển thị trực tiếp nội dung Word như một tệp Markdown; thành viên thường phải tải xuống để đọc.
    
-   Markdown (`.md`) là văn bản thuần có cú pháp định dạng, nên GitHub có thể hiển thị trực tiếp dưới dạng tài liệu dễ đọc.
    

Sai lầm 2: Cho rằng Git có thể so sánh mọi định dạng tệp giống nhau.

-   Git xử lý tệp Word thường như dữ liệu nhị phân (binary), khiến việc xem khác biệt giữa các phiên bản khó khăn.
    
-   Markdown là văn bản thuần (plain text), nên Git Diff có thể chỉ ra chính xác dòng hoặc ký tự đã thay đổi, giúp nhóm xử lý xung đột thuận tiện hơn.## 2. Tại sao Markdown nhẹ và an toàn hơn?

Tiêu  chí

Word  (.docx)

Markdown  (.md)

Bản  chất

Gói  dữ  liệu  định  dạng,  thường  là  ZIP  chứa  XML  và  tài  nguyên

Văn  bản  thuần

Dung  lượng

Thường  lớn  hơn  do  định  dạng  và  tài  nguyên  nhúng

Thường  nhẹ  hơn

Git  Diff

Khó  so  sánh  trực  tiếp  nếu  không  có  công  cụ  hỗ  trợ

Dễ  xem  từng  dòng  thay  đổi

Hiển  thị  GitHub

Thường  cần  tải  xuống  hoặc  dùng  công  cụ  phù  hợp

Hiển  thị  trực  tiếp

Khả  năng  phục  hồi

Có  thể  bị  lỗi  cấu  trúc  khi  dữ  liệu  quan  trọng  bị  hỏng

Có  thể  đọc  và  cứu  phần  văn  bản  còn  nguyên  dễ  dàng  hơn

Bẫy dữ liệu — mất 1 byte: Không thể kết luận rằng mất một byte sẽ luôn làm hỏng hoàn toàn tệp Word. Tuy nhiên, nếu byte bị mất nằm trong phần cấu trúc quan trọng của gói `.docx`, tệp có thể không mở được. Markdown không có cấu trúc gói phức tạp như vậy; nếu mất một byte, thường chỉ một ký tự hoặc một phần văn bản bị ảnh hưởng, còn phần nội dung khác vẫn có thể đọc được.

Lưu ý, Markdown cũng không miễn nhiễm với mất dữ liệu. Ưu thế của nó là cấu trúc đơn giản, dễ kiểm tra, dễ phục hồi và phù hợp với hệ thống quản lý phiên bản Git.



## Phần 1. Phân tích lỗi

1. Vì sao định dạng thủ công gây lỗi mục lục?

Nam chỉ phóng to chữ, in đậm hoặc đổi màu nhưng vẫn để kiểu Normal. Word không nhận diện đây là tiêu đề nên khi tạo mục lục tự động (Auto TOC), xuất hiện thông báo `No table of contents entries found`.

2. Lỗi gán Heading 1 sai

Nam gán Heading 1 cho một đoạn văn dài 5 trang. Word hiểu toàn bộ đoạn đó là tiêu đề và đưa vào mục lục. Cần chuyển đoạn văn về Normal, chỉ giữ Heading Styles cho các dòng tiêu đề thực sự.

## Phần 2. Sửa lỗi

Bước 1: Gán Heading Styles đúng cấp

-   Chọn `1. Giới thiệu` → Home → Styles → Heading 1.
    
-   Chọn `2. Yêu cầu chức năng` → Heading 1.
    
-   Các tiêu đề mục con như `2.1. Đăng nhập`, `2.2. Đặt cơm` → Heading 2.
    
-   Chọn đoạn văn dài 5 trang → chuyển về Normal.
    
-   Nội dung thông thường sử dụng Normal, không gán Heading 1 hoặc Heading 2.
    

Bước 2: Chèn lại mục lục tự động

1.  Xóa mục lục cũ đang bị lỗi.
    
2.  Đặt con trỏ tại vị trí cần chèn mục lục.
    
3.  Chọn References → Table of Contents → Automatic Table.
    
4.  Kiểm tra mục lục đã hiển thị đúng tiêu đề và số trang.
    

Bước 3: Cập nhật mục lục

Sau khi thêm hoặc sửa nội dung:

1.  Nhấp vào mục lục.
    
2.  Chọn Update Table.
    
3.  Chọn Update entire table để cập nhật cả tiêu đề và số trang.
    

## Kết luận

Nam cần sử dụng Heading Styles thay cho định dạng thủ công, phân cấp tiêu đề đúng và cập nhật Auto TOC sau mỗi lần chỉnh sửa. Nhờ đó, mục lục sẽ chính xác, dễ quản lý và không xuất hiện các đoạn văn dài sai vị trí.
