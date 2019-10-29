### Vue组件通信





##### props属性

> props属性是开发中最常用的一种组件通信通讯方式 , 父组件中在组件标签上定义属性 , 子组件内定义props接收
>
> 父->子通信

###### parent.vue父组件

```vue
<tempalte>
	<Child msg="hello word"></Child>
</template>
```

###### child.vue子组件

```vue
<tempalte>
	<h1>{{msg}}</h1>
</template>
<script>
export default{
	props:{
    msg:{
      type:String,
      default:''
    }
  }
}
</script>
```



##### $emit & \$on

> $emit触发当前实例事件 , 附加参数会传给监听器回调
>
> \$on监听当前实例上的自定义事件。事件可以由vm.$emit触发。回调函数会接收所有传入事件触发函数的额外参数 
>
> 子->父通信

###### child.vue子组件

```vue
<tempalte>
	<button @click="onClick">lalala</button>
</template>
<script>
export default{
  data(){
    return {
      test:'我是子组件child的test'
    }
  }
}
</script>
```

###### parent.vue父组件

```vue
<tempalte>
	<Child msg="hello word"></Child>
</template>
```









































