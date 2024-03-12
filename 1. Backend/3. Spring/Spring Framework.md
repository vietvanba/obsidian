# Hai nguyên tắc thiết kế chính là :
+ Dependency injection và Aspect oriented programming
# Dependency Injection và Inversion of control
+ Dependency Injection là một design pattern quan trọng trong spring framework-> Giúp loại bỏ sự phụ thuộc lẫn nhau giữa các thành phần của ứng dụng
+ Inversion of control: Container trong spring chịu trách nhiệm khởi tạo, cấu hình kết nối các đối tượng
	+ Gồm 2 loại
		+ BeanFactory
		+ ApplicationContext
# Các module quan trọng của Spring Framework
## Core Container
Bao gồm
+ spring-core
+ spring-beans
	+ **spring-core** và **spring-beans** cung cấp các phần cơ bản của framework, bao gồm **IoC** và **Dependency Injection**. `Spring Bean` được coi như linh hồn của ứng dụng Spring.
+ spring-context
	+ hỗ trợ đa ngôn ngữ (internationalization) và tích hợp các tính năng Java EE như EJB và JMX.
+ spring-expression
	+ cung cấp hỗ trợ cho việc đặt và lấy giá trị, toán tử logic và truy cập các tập hợp dữ liệu.
## Data Access/Integration
**Data Access/Integration** bao gồm các module JDBC, ORM, OXM, JMS và Transaction.
- **spring-jdbc** giúp giảm thiểu mã JDBC và hỗ trợ nhiều cơ sở dữ liệu.
- **spring-orm** tích hợp với các orm API phổ biến như JPA, JDO và Hibernate.
- **spring-oxm** hỗ trợ Object/XML mapping với nhiều công cụ như AXB, Castor, XMLBeans và nhiều công cụ khác.
- **spring-jms** cung cấp khả năng tạo và sử dụng các message và tích hợp với **spring-messaging**.
- **spring-transaction** hỗ trợ quản lý giao dịch cho các POJO và các lớp đặc biệt.
## Web
Spring cung cấp **Spring MVC** để xây dựng ứng dụng web. Module bao gồm: **spring-web**, **spring-webmvc**, **spring-websocket** và **springwebmvc-portlet**.

- **spring-web** hỗ trợ tích hợp web, chức năng tải tệp và khởi tạo **IoC container** sử dụng servlet.
- **spring-webmvc** triển khai Model-View-Controller (MVC) cho ứng dụng web.
- **spring-websocket** hỗ trợ WebSocket-based, giao tiếp hai chiều giữa client và server trong các ứng dụng web.
- **springwebmvc-portlet** dành cho môi trường portlet và ánh xạ chức năng của **module Web-Servlet**.

### AOP, Aspects, Instrumentation và Messaging

Những module này hỗ trợ lập trình hướng khía cạnh (Aspect Oriented Programming) và tích hợp với AspectJ.

- **Module AOP** cung cấp lập trình hướng khía cạnh, cho phép tách rời mã và các chức năng của ứng dụng.
- **Module Aspects** tích hợp với AspectJ, một khuôn khổ AOP mạnh mẽ.
- **Module Instrumentation** hỗ trợ đo đạc và triển khai lớp bộ nạp.
- **Module Messaging** hỗ trợ STOMP và WebSocket, cung cấp mô hình lập trình chú thích cho định tuyến và xử lý tin nhắn STOMP.