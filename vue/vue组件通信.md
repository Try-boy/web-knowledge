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























### 协同&复用方案

#### 针对GIS

**Cesium二次封装(核心2个)：**

- **api简化**

- **功能封装**



##### 封装好的cesium包管理

对于封装好的cesium，其实就是一个js包，我们这边可以放到一个单独的git仓库

如果将来进行小功能迭代，不影响其他项目使用，直接在分支上更新操作

对于大模块更新的话，建立分支管理不同版本，以版本号命名分支

每次更改影响上一个包的使用视为大版本更新，老版本推到其他分支，新版本在主分支迭代

迭代久了，就和之前那家公司给我们的sdk差不多，就是一个小型cesium库了，但是是符合我们公司风格的

有新人参与开发，可以直接看文档，相对会比直接看cesium文档简单，因为我们只封装对公司开发有用的



#### 项目复用

开发一个公用的脚手架，模块划分比较细的cli，这样其他人在改代码时只需要熟悉一套cli风格就可以了

项目代码复用不太现实，只会越来越乱

但是只要脚手架风格相同，其实中间就会有很多可以复用的地方，结构都是一样的

这套cli管理也和封装的cesium一样，通过git管理，不断迭代，但是大体风格是不会变的，迭代也只是官方版本更新了，我们这边再进行更新

公司前端以后开发vue项目都可以使用这套cli，这样好处就是在一个人改另一个人代码时，清晰明了，只需要看功能就可以了，结构都是一样的



大概是这样，你看这个方案行不行，可以的话等下找个时间叫浩强他们开个会细说一下，我给他们细说下封装好的cli结构和开发方式



















