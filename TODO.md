[[进程间通信]]
- [[AIDL]]
[[Handler]]
移动端和车机端的开发区别
推送的底层实现

livedata的postvalue和setvalue
- setValue 只能在主线程
- postValue 可以在子线程。如果多次调用，在主线程执行更新之前，只会保存最后一次的值
自定义view
点击事件分发
- dispatchTouchEvent
- onTouch (有返回值，返回true表示事件被消费)
- onTouchEvent
- onClick
协程
动画
内存泄漏场景