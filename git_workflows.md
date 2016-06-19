# So sánh các quy trình làm việc với git
\** Mình xin phép không dịch một số thuật ngữ (vì không biết dịch thế nào cho đúng)*

*Sự đa dạng các quy trình làm việc với Git có thể làm cho chúng ta khó khăn khi tiếp cận và mong muốn áp dụng vào môi trường làm việc của mình. Vì vậy, bài post này nhằm mong muốn đem lại cho mọi người cái nhìn rõ ràng về một vài quy trình phổ biến nhất.*

*Lưu ý rằng, các quy trình này đơn thuần chỉ là các hướng dẫn chứ không phải là những luật lệ cụ thể. Vì thế bạn có thể áp dụng hoặc phối hợp các yếu tốt với nhau để phù hợp hơn với mô hình công ty của mình.*
## Quy trình tập trung (Centralized Workflow)
![centrailize_1](https://www.atlassian.com/git/images/tutorials/collaborating/comparing-workflows/centralized-workflow/01.svg)
Đây là cách tiếp cận đơn giản nhất cho các nhóm đã quen với Subversion (SVN). Chuyển đổi quy trình làm việc sang hệ thống distributed version control (như Git) là một việc khá khó khăn, nhưng bạn không nhất thiết phải thay đổi hoàn toàn đổi sang quy trình phân tán mới tận dụng được các lợi ích của Git. Nhóm của bạn vẫn có thể dùng Git y hệt như cách đã sử dụng trên Subversion.

Tuy sử dụng như Subversion nhưng chúng ta vẫn có được những ưu thế từ Git. Đầu tiên, Git giúp các developer có được một bản back dữ liệu ở máy cá nhân. Sự cô lập này giúp các developer có thể làm việc độc lập với các thay đổi khác của dự án - cụ thể, họ có thể commit vào local repository và tiếp tục công việc mà không cần phải nhớ tất cả các thay đổi của mình.

Thứ hai, Nó giúp bạn tiếp cận với 2 mô hình tốt của Git là branching và merging. Không giống như SVN, Git branching được thiết kế trên fail-safe mechanism giúp cho việc tích hợp và chia sẻ code với các repository khác nhau.

### Quy trình

Giống với SVN, Centralized Workflow sử dụng một central reposiroty để phục vụ cho việc quản lý tất cả các thay đổi của project. Thay vì **trunk** trong SVN, branch mặc định trong Git được gọi là **master** và tất cả các thay đổi sẽ được commit vào branch này. Với quy trình này, thì không cần bất kỳ một branch nào khác ngoài master.

Các developer bắt đầu làm việc bằng cách clone central repository. Bên trong local repository, họ chỉnh sửa file và commit y hệt cách họ làm với SVN; Thy nhiên, những commit này được lưu ở máy cá nhân - và chúng hoàn toàn cô lập với central repository. Cách tiếp cận này giúp các developer trì hoãn việc đồng bộ các với central repository, cho đến khi nào nào họ cảm thấy thuận tiện nhất.

Để đưa các thay đổi của mình vào project chính thức, developer **push** local master branch của họ lên central repository. Nó bằng với ```svn commit```, trừ một điểm đó là nó thêm tất cả các local commit vào central repository.
![centralize_2](https://www.atlassian.com/git/images/tutorials/collaborating/comparing-workflows/centralized-workflow/02.svg)

### Quản lý conflict

1. 

