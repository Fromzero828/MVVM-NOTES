## 生命周期<br />

### Angular指令生命周期钩子的作用及调用顺序
  * 1 constructor：组件的构造函数会在所有的生命周期钩子之前被调用，它主要用于依赖注入或执行简单的数据初始化操作。
  * 2 ngOnChanges：当数据绑定输入属性的值发生变化时调用
  * 3 ngOnInit：在第一次 ngOnChanges 后调用
  * 4 ngDoCheck：自定义的方法，用于检测和处理值的改变
  * 5 ngAfterContentInit：在组件内容初始化之后调用
  * 6 ngAfterContentChecked： 组件每次检查内容时调用
  * 7 ngAfterViewInit：组件相应的视图初始化之后调用
  * 8 ngAfterViewChecked：组件每次检查视图时调用
  * 9 ngOnDestroy：指令销毁前调用

### constructor
组件的构造函数会在所有的生命周期钩子之前被调用，它主要用于依赖注入或执行简单的数据初始化操作。

### ngOnChanges
当数据绑定输入属性的值发生变化的时候，Angular 将会主动调用 ngOnChanges 方法。它会获得一个 SimpleChanges 对象，包含绑定属性的新值和旧值，它主要用于监测组件输入属性的变化。

### ngOnInit
在第一次 ngOnChanges 执行之后调用，并且只被调用一次。它主要用于执行组件的其它初始化操作或获取组件输入的属性值。

### ngDoCheck
当组件的输入属性发生变化时，将会触发 ngDoCheck 方法。我们可以使用该方法，自定义我们的检测逻辑。它也可以用来加速我们变化检测的速度。

### ngAfterContentInit
在组件使用 ng-content 指令的情况下，Angular 会在将外部内容放到视图后用。它主要用于获取通过 @ContentChild 或 @ContentChildren 属性装饰器查询的内容视图元素。

### ngAfterContentChecked
在组件使用 ng-content 指令的情况下，Angular 会在检测到外部内容的绑定或者每次变化的时候调用。

### ngAfterViewInit
在组件相应的视图初始化之后调用，它主要用于获取通过 @ViewChild 或 @ViewChildren 属性装饰器查询的视图元素。

### ngAfterViewChecked
组件每次检查视图时调用

### ngOnDestroy
在指令被销毁前，将会调用 ngOnDestory 方法。它主要用于执行一些清理操作，比如：移除事件监听、清除定时器、退订 Observable 等。
