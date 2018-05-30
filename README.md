# myJS
some scripts I usually used in my project.
the file myJS.js is can be used in any script,you just have to inport it in your <script></script> Tag.
the file mgJS-ES6 is for ES6 programing。just import it with "import mgJS from '...' 

包含但不仅限以下api：

		A()
		选择器
		 selector：
		 	object:获取对象,
		 	id:根据id获取html对象
		 	className:根据className获取html对象集合
		 	tagName:根据tagName获取html对象集合
		extend：
			1).A.extend(a,b)：根据b对象,为对象a进行扩展。
			2).A.fn.extend为A框架选择的对象扩展扩展方法
		attr(a,b)
			1).两个参数如ele.attr(a,b)：改变元素的attribute值
			2).一个参数如ele.attr(a)：获取attr的的值
		html(str)
			1).带参数：修改html文本
			2).无参数：获取html文本
		on(type,fn) 
			监听事件
			注意，此处通过惰性模式，在该库加载时就立即执行on函数，重新定义on函数。减去了多个分支，提高性能
		getClientTop()
			获取元素相对浏览器上部高度
		getClientLeft()
			获取元素相对浏览器左侧高度
		getDocumentSize
			获取浏览器文档高度和长度
			返回：一个对象，height属性为高度，width属性为长度
		EventUtil：跨浏览器的事件处理对象
			1).removeHandler(ele,eventName,handler)
				移除事件
				参数：
					ele:注册事件的元素
					eventName：事件的类型
					handler:事件
			2).getEvent(event)
				跨浏览器获取事件
				参数:
					event：事件对象 
			3).getTarget(event)
				跨浏览器获取当前事件的目标
				参数:
					event：事件对象 
			4).preventDefault
				乱浏览器取消默认事件
				参数:
					event：事件对象 
			5).stopPropagation
				跨浏览器取消冒泡
				参数:
					event：事件对象 
		entrust_on(parentEle,eventName,selector,handler)
			事件委托
				事件委托
				 eventName:
				类型:String
				定义:事件名字
				 parentEle:
				 类型:nodeType
				定义:将要注册事件的父元素
				selector:
				类型:String
				定义:选择器，可以是className或者tagName
				handler:
				类型:function
				 定义:事件的执行函数
		Cookie:
			Cookie对象封装的方法：
				setCookie(name,value,iDay):
					定义：添加cookie
					name:
					 	类型:string
					 	定义:cookie名
					value:
						类型:value
						定义:cookie值
					iDay:
						类型:number
					 	定义:cookie保存时间
				getCookie(name)
					定义：获取cookie
					name:
					 	类型:string
					 	定义:cookie名
				removeCookie(name)
					name:
					 	类型:string
					 	定义:cookie名
		newSort(arr,sortMethods)
			arr:要重新排序的数组
			sortMethods：排序方法
				'up'：代表升序,
				'dowm'：代表降序
		countUp(deadline)
			定义：计时，隔秒输出数字0~deadline
			参数
			    deadLine:
					类型:number
					定义:倒计时间长度
		countDown(deadline)
			定义：计时，隔秒输出数字deadline~0
			参数
			    deadLine:
					类型:number
					定义:倒计时间长度
		deepCopy(initObj,newObj)
			深拷贝（递归实现）
			initObj:被拷贝对象
			newObj：新的对象（可选）
			返回：新的对象
		mobileRemSizingByWangYi(rate)
			
			网易rem移动布局
			把理想视口设置为布局视口
			根据设计图宽度动态设置字体大小为100px;
			设计图中所有的尺寸都除以100得出以rem单位的值
			字体大小采用媒体查询
			参数：
				rate:设计图宽度/100所得值

		imageLazyLoad()
		    图片懒加载
		    (使用节流器优化性能)

		throttle()
			节流模式(节流器)
			throttle接受两个参数
			参数1：要执行的函数
			参数2：一个对象，
			{
					context: null,//表示函数的作用域
					args: [],//函数的参数
			 		time:300 //节流的时间间隔，即多个函数的触发时间间隔小于此时间，则只执行最后一个函数
			}
		decoration(dom,type,fn)
			装饰者模式:在不改变原有事件的基础上，为元素添加新的事件
			参数：	
				dom:元素对象
				type：事件类型
				fn:事件处理函数
		formateString(str,data)
			简单模板模式
			定义：通过格式化字符串拼凑出视图避免创建视图时大量节点操作
			参数：
				str:模板字符串:如<span>{#span#}</span>
				data:添加到模板字符串的数据，如{span:'this is the data for label "span" '}
		view
			模板生成器
			类型：对象
			方法：
				addTp(name,tp)
				添加模板
				参数：
					name:模板名称
					tp:模板字符串{#数据名（必须要跟传入的数据的属性名相对应）#}
		create(tag,attrs)
			创建html元素
			参数:
				tag:标签名
				attrs:
					添加特性的对象
		toArray(html_collection)
			html集合转数组
			参数：
				html_collection：html集合，如：document.getELementByTagName(Tagname)返回的html集合
		menoize
			使用缓存，把以产生的计算结果缓存下来，方便下次使用。避免在多次调用函数时，重复计算。
			fn:
				定义: 原函数的函数名
				类型: function	
			cache：
				定义：可预先设定的缓存
				类型：object
		processArray(items,process,callback)：
			使用定时器处理数组，避免循环语句长时间运行脚本导致浏览器假死
			参数：
				items:数组
				process：数组成员处理函数
				callback：执行完的回调
		multiStep(steps,args,callback)
			若一个任务可以被分解成多个任务，使用定时器处理多个任务，避免长时间运行脚本导致浏览器假死
			参数：
				steps:任务的函数名的数组
				args：处理函数的参数
				callback：执行完的回调

		handleImageData(data,mimeType)
			使用multipart xhr技术生成的多图片分割后，对图片进行处理
		    参数：
				data：图片转换后的base64字符串
				mimeType：图片类型
		handleCss:(data)
			使用multipart xhr技术生成的多css分割后，把css样式添加到文档中
			参数：
				data：css样式代码
		handleJavaScript:(data)
			使用multipart xhr技术生成的js分割后，把js代码执行
			参数：
				data：javascript代码
		getUrlParams:(url)
			URL中查询字符串中的参数
			参数：
				url:要获取查询字符串的的url
			若无参数：则获取当前页面的url
