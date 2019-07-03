<!doctype html>
<html>
<head>
	<meta charset="utf-8" />
	<title>Web Component</title>
	<link rel="stylesheet" type="text/css" href="./demos/demo.css" />
<style type="text/css">
.my-slot {
	color: red;
}

/* 浏览器还不支持，可以嵌套在任何层级上 */
:root::theme(test) {
  color: blue;
}

/* 有效，只能作用于特定的选择器上 */
my-element::part(test) {
	background-color: yellow;
}

/* 无效 */
my-element::part(test) div {
	background-color: red;
}
/* 外部样式优先级高于内部样式 */
my-element {
	border: 2px solid blue;
}
</style>
</head>
<body>

<div class="code">
	<div>参考文档：</div>
	<div>https://github.com/w3c/webcomponents</div>
	<div>https://github.com/topics/web-components</div>
	<div>https://github.com/mdn/web-components-examples</div>
	<div>https://developer.mozilla.org/zh-CN/docs/Web/Web_Components</div>
	<div>https://www.cnblogs.com/zhaowinter/p/5447246.html</div>
	<div>https://juejin.im/post/5cb3f5b95188251add7f11bc</div>
	<div>https://www.webcomponents.org/</div>
</div>

<div class="code">
	<button id="btn-disable">disable</button>
	<button id="btn-enable">enable</button>
</div>

<div class="code">
	<h1>
		被h1元素包裹的自定义元素，显示为绿色
		<my-element></my-element>
	</h1>
</div>

<div class="code">
	<my-element>
		<div slot="header" class="my-slot">header slot</div>
		<div class="my-slot">未命名 slot</div>
	</my-element>
</div>

<script type="text/javascript">
/*
Web Components开发组件是用customElement做外壳，在其中建立shadowDOM，将模板放到shadowDOM中，形成一个html页面，使用时通过HTML Import引入
*/

// 生命周期顺序：
// constructor -> [attributeChangedCallback] -> connectedCallback -> disconnectCallback
class MyElement extends HTMLElement {
	static get observedAttributes() {
		return ['disabled', 'foo', 'bar']
	}

	constructor() {
		super()
		// this.container = this.shadowRoot.querySelector('#container');
		// 将 mode设置为 open 表示你可以通过页面内的 JavaScript 方法来获取 Shadow DOM，例如使用Element.shadowRoot
		// 将 mode设置为 closed，那么就不可以在外部获取 Shadow DOM了——myCustomElem.shadowRoot 将会返回 null，比如video元素
		const shadowRoot = this.attachShadow({mode: 'open'});
		shadowRoot.innerHTML = `
		  <style>
			:host {
				all: initial;
				display: block;
				width: 300px;
				height: 120px;
				border: 1px solid #eee;
				background: #fff;
			}
			:host([disabled]) {
				display: inline-block;
				opacity: 0.4;
			}
			/* 自定义元素 必须是h1的子孙元素 才能匹配 */
			:host-context(h1) {
				color: green;
			}
		  </style>

		  <div id="container" class="container" part="test">
		  	<div>【点我试试】</div>
			<slot name="header"></slot>
			<slot name="body">没有定义body slot时，这行文字会出现</slot>
			<slot name="footer"></slot>
			<slot />
		  </div>
		  <script>
		  	console.log('这段代码不会被执行')
		  <\/script>
		`;

		this.container = shadowRoot.querySelector('#container');
		console.log(shadowRoot)
		// console.log(shadowRoot.querySelector('script'))
	}

	// 当 custom element被插入文档DOM时，被调用
	connectedCallback() {
		console.log('-----------------------------', '元素被插入文档')
		console.log('根节点: ', this.getRootNode())
		console.log('isConnected: ', this.isConnected)
		this.shadowRoot.addEventListener('click', this.handleClick)
	}
	// 当 custom element从文档DOM中删除时，被调用
	disconnectedCallback() {
		console.log('-----------------------------', '元素被移出文档')
		console.log('isConnected: ', this.isConnected)
		this.shadowRoot.removeEventListener('click', this.handleClick)
	}
	// 当 custom element被移动到新的文档时，被调用
	adoptedCallback() {
		console.log('-----------------------------', '元素被移动到其他文档')
	}
	// 当 custom element增加、删除、修改自身属性时，被调用
	// 这个方法只有当被保存在 observedAttributes 数组的属性改变时，就如这个例子中的disabled，被改变才会调用，其他属性改变则不会
	attributeChangedCallback(attrName, oldValue, newValue) {
		console.log('-----------------------------', '元素属性改变了')
		console.log(attrName, oldValue, newValue)
		switch (attrName) {
			case 'disabled':
				if(this.disabled) {
					this.container.style.background = 'red'
				} else {
					this.container.style.background = '#ffffff'
				}
				break;
			case 'foo':
				// statements_1
				break;
			case 'bar':
				// statements_1
				break;
			default:
				// statements_def
				break;
		}
	}

	handleClick(e) {
		// https://developer.mozilla.org/zh-CN/docs/Web/API/Event/Event
		this.dispatchEvent(new CustomEvent('menu-click', {
			detail: {
				message: '这是一个自定义事件'
			},
			// 表示该事件是否冒泡
			bubbles: false,
			// 表示该事件能否被取消
			cancelable: false,
			// 用来指示该事件是否可以从 Shadow DOM 传递到一般的 DOM。
			composed: true
		}))
	}

	test() {
		console.log('这是一个自定义方法~~')
	}

	set disabled(newVal) {
		if(newVal) {
			this.setAttribute('disabled', 'true');
		}
		else {
			this.removeAttribute('disabled');
		}
	}

	get disabled() {
		return this.hasAttribute('disabled');
	}
}


// customElements.upgrade 的用法，主要用于createElement创建的未升级的dom
// 可以升级一个dom树，包括其子孙节点，如果没有需要升级的节点也不会报任何错误
{
	console.log('==============================')
	const el = document.createElement("spider-man");
	class SpiderMan extends HTMLElement {}
	customElements.define("spider-man", SpiderMan);
	console.log(el instanceof SpiderMan); // not yet upgraded
	customElements.upgrade(el);
	console.log(el instanceof SpiderMan);    // upgraded!
}


{
	console.log('==============================')
	// :unresolved @deprecated
	// const unresolvedElements = document.querySelectorAll(':unresolved');
	const undefinedElements = document.querySelectorAll(':not(:defined)')
	console.log('undefined Elements: ', undefinedElements)
	const promises = [...undefinedElements].map(
		undefinedEle => customElements.whenDefined(undefinedEle.localName)
	)
	Promise.all(promises).then(() => {
		console.log('my-element is defined now!')
	})
}

console.log('==============================')
// 注册 自定义元素
window.customElements.define('my-element', MyElement)
// 获取 已注册的自定义元素构造函数
const myEleClass = customElements.get('my-element')

// 创建一个自定义元素实例
const myElement = new myEleClass()
myElement.classList.add('test-cls')
// 添加到文档
document.body.appendChild(myElement)
myElement.test()


document.querySelector('#btn-disable').addEventListener('click', function(evt) {
	myElement.disabled = true
})
document.querySelector('#btn-enable').addEventListener('click', function(evt) {
	myElement.disabled = false
})
myElement.addEventListener('my-ele-mounted', function(evt) {
	console.log(evt)
	console.log(evt.detail.message)
})


</script>

</body>
</html>
