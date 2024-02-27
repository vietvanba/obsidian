# Async Promise
+ Async được dùng để khai báo hàm chỉ định rằng hàm số đó sẽ chứa một hoặc nhiều wait 
+ Async sẽ tự động trả về một promise và luôn trả về một promise bất kể nó trả về một giá trị khác
+ Promise là một cơ chế xử lý các tác vụ bất đồng bộ
+ có 3 trạng thái của promise
	+ pending (chờ)
	+ fulfilled (thành công)
	+ rejected (bị từ chối)
+ 
## preventDefault
+ dùng để ngăn chặn hoạt động mặc định. ví dụ như là khi nhấp vào liên kết thì trình duyệt sẽ thực hiện điều hướng đến URL trong tag href. thì preventDefault sẽ ngăn chặn hành động mặc định này. ví dụ như trong form cũng vậy. dùng để tùy chỉnh submit
# Reduce

# Lambda
# hook 
+ useState
+ useEffect
	+ tương ứng với componentDidMount
	+ componentDidUpdate
	+ componentWillUnMount
+ useMemo
+ useCallBack
+ useReducer
# state 
# props
# render 
+ Khi component cha được render lại thì component con cũng sẽ được render lại 
+ để tránh việc render lại thì ta dùng React.memo đối với function component và PureComponent với Class component
# lifecycle
+ Mounting
	+ contructor
	+ render
	+ DidMount (Chỉ Chạy một lần duy nhất, thường dùng để call api)
+ Updating
	+ Didupdate( có thể gọi nhiều lần)
+ UnMounting
	+ willUnmount(chỉ gọi một lần duy nhất trước khi hủy bỏ, dùng để huy timeout, clearInterval)

# Localstorage 
# session 
# cookies

# Var  
+ Global scope ( có thể truy cập ở bất kì đâu trong chương trình)
+ Hosting : Giá trị khởi đầu là undefined 
+ Có thể cập nhật hoặc khai báo lại
# let
+ Block scope (được khai báo trong 1 block (if , func ,...) và chỉ có thể truy cập ở trong block dó) 
+ Hosting: Không có giá trị khởi đầu
+ Không thể khai báo lại chỉ có thể cập nhật lại
# const
+ Block scope (được khai báo trong 1 block (if , func ,...) và chỉ có thể truy cập ở trong block dó) 
+ Hosting: Không có giá trị khởi đầu
+ Không thể khai báo hoặc cập nhật lại

# Es5 es6