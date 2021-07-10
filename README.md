# mockVue
仿写Vue的双向绑定
如上两种实现方式，本质上是相同的，只是在数据响应式上的实现不一样，
方法一是自身写的观察者械Event,
方法二是利用js本身自带的方法EventTarget来实现的

“响应式”，是指当数据改变后，会通知到使用该数据的代码。例如，视图渲染中使用了数据，数据改变后，视图也会自动更新。
数据响应式实现原理：
  1. 利用数据劫持 (defineProperty, Proxy) 监听对应数据的修改设置
  2. 利用观察者模式(或事件机制),给每一项数据添加相应的事件监听，当数据修改时触发该事件，然后驱动视图进行修改

双向绑定：
 1. 利用数据响应式，完成数据对视图修改
 2. 添加 change 或 input 等事件，监听视图的修改，当视图改变时修改数据


