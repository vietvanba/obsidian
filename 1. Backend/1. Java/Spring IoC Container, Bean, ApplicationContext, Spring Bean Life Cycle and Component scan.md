# Spring IoC Container
+ Spring IoC Container stand for `Spring Inversion of Control Container`
+ IoC(Inversion of Control): Đảo ngược điều khiển, nó giúp làm thay đổi luồng điều khiển của chương trình một cách linh hoạt.
+ IoC Container sẽ tạo ra các đối tượng, lắp ráp chúng lại với nhau, cấu hình các đối tượng và quản lý các vòng đời của chúng từ lúc tạo ra đến lúc bị huỷ.
+ Sử dụng cơ chế DI ( Dependency injection ) để quản lý các thành phần
# BeanFactory ApplicationContext
## BeanFactory
- `BeanFactory` là gói dịch vụ cơ bản nhất trong Spring, cung cấp khả năng tải, cấu hình và quản lý các bean trong ứng dụng của bạn.
- Nó là một giao diện (interface) chứa các phương thức cơ bản để truy cập các bean trong Spring Container.
- BeanFactory **hoạt động theo nguyên tắc "lazy-loading"**, điều này có nghĩa là các bean chỉ được tạo ra khi cần thiết, không phải tất cả các bean đều được tạo ra khi Spring Container được khởi tạo.
## ApplicationContext 
+ `ApplicationContext` là một phần mở rộng của `BeanFactory`, cung cấp tất cả các tính năng của `BeanFactory` cũng như nhiều tính năng mở rộng khác.
- Nó là một giao diện mạnh mẽ hơn, cung cấp các tính năng như quản lý vòng đời của các bean, event publishing, quản lý tài nguyên (resource management), và các tính năng khác như internationalization.
- `ApplicationContext` thường được ưu tiên hơn `BeanFactory` trong phần lớn các ứng dụng Spring, do nó cung cấp nhiều tính năng hơn và linh hoạt hơn.
- `ClassPathXmlApplicationContext`, `AnnotationConfigApplicationContext`, và `FileSystemXmlApplicationContext` là các triển khai tiêu biểu của `ApplicationContext`, cho phép bạn cấu hình ứng dụng của mình bằng cách sử dụng các cấu hình Java, XML hoặc cả hai.
# Bean
+ Bean là một đối tượng do Spring quản lý
+ Bean nằm trong Spring IoC Container 
+ Bean có thể là bất kì đối tượng nào trong ứng dụng của bạn từ service đến repository đến DTO hoặc config của ứng dụng
+ để Spring biết được đối tượng cụ thể nào trong ứng dụng là bean thì chúng ta cần dùng các annotation như `@Component`, `@Service`, `@Repository`, hoặc `@Configuration`
## Cách inject bean và một bean khác
### 1. @AutoWire
```java
@Component public class Car {
	// Báo cho Spring tìm bean nào phù hợp với Engine interface 
	// Và có một bean phù hợp là ChinaEngine 
	// Nó tương đương với = new ChinaEngine() 
	@Autowired 
	private final Engine engine; 
}
```
### 2. Inject qua constructor
```java
@Component 
public class Car { 
	private final Engine engine; 
	public Car(Engine engine) { 
		this.engine = engine; 
	} 
}
```
### 3. Inject qua setter
```java
@Component 
public class Car { 
	private final Engine engine; 
	// Thêm @Required để setter luôn được gọi để inject 
	@Required 
	public void setEngine(Engine engine) { 
		this.engine = engine; 
	} 
}
```
+ Cách dùng setter để inject thường dùng trong trường hợp phụ thuộc vòng, module A phụ thuộc vào B và ngược lại. Do đó, nếu cả hai đều sử dụng constructor based injection thì Spring Boot sẽ không biết nên tạo bean nào trước. Vì thế, giải pháp là một bean sẽ dùng constructor, một bean dùng setter như trên.
## Khi Spring Boot không biết chọn bean nào?
+ Khi tìm thấy nhiều bean phù hợp
	+ Giải pháp:
		+ Dùng `@Primary` để đánh dấu một bean là bean mặc định. khi đó bean này sẽ được ưu tiên hơn
		+ Dùng `@Qualifier` để chỉ định rõ tên bean 
## Spring Bean Life Cycle
![[Pasted image 20240314222659.png]]
+ Constructor 
+ Setter method
+ @PostConstruct
+ Init method
+ Bean is already
+ @PreDestroy
### @PostConstruct và @PreDestroy
+ `@PostConstruct` đánh dấu method sẽ được chạy sau khi bean khởi tạo xong
+ `@PreDestroy` đánh dấu method sẽ được chạy trước khi bean được phá huỷ
+ `@PostConstruct` thường được dùng để **Thiết lập giá trị mặc định**, **Khởi tạo các tài nguyên bên ngoài**, **Kết nối và thiết lập liên kết**
+ `@PreDestroy` thường được dùng để thực hiện các tác vụ dọn dẹp