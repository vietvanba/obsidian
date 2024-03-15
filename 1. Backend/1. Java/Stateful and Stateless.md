| Tiêu chí        | Stateless                                                                      | Stateful                                                                               |
| --------------- | ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------- |
| Định nghĩa      | Là trạng thái không lưu các dữ liệu của client trên server                     | Là trạng thái lưu dữ liệu của client trên server                                       |
| Ví dụ           | HTTP, DNS, UDP                                                                 | FTP, Telnet                                                                            |
| Hạn chế máy chủ | Máy chủ không cần lưu giữ thông tin máy chủ hoặc các chi tiết cho phiên của nó | Máy chủ được lưu giữ để yêu cầu duy trì trạng thái hiện tại & thông tin phiên làm việc |
| Sự phụ thuộc    | Máy chủ và máy khách được kết hợp lỏng lẻo, có thể hoạt động độc lập           | Máy chủ và máy khách có sự ràng buộc chặt chẽ                                          |
| Thiết kế        | Thiết kế máy chủ đơn giản                                                      | Thiết kế máy chủ phức tạp & khó thực hiện                                              |
| Sự cố           | Khi có sự cố, máy chủ dễ dàng khởi động lại                                    | Máy chủ phải lưu giữ nhiều thông tin khác nhau nên rất khó quản lý sự cố               |
| Tốc độ          | Máy chủ xử lý nhanh chóng các giao dịch                                        | Tốc độ khá chậm                                                                        |
