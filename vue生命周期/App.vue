<template>
<div >
  <el-button type="primary" @click="aaa">1234</el-button>
{{time}}
</div>
</template>

<script>
  export default {
    data() {
      return {
          time:new Date()
      }
    },
    methods:{
      aaa(){
     this.time="12345678"
      }
    },
    beforeCreate () { //此时vue实例还没有创建
      console.log('%c%s','color:blue','beforeCreate的data内容'+this.time);
    },
    created(){ //此时 vue实例已经创建好 已经有data的监听和methods事件 
    //之后判断有没有template 有就把data里的数据和模板里的vue语法翻译成html 没有 就把el元素及其后代(outHtml)作为template
      console.log('%c%s','color:blue','created的data内容'+this.time);
      this.time='3333' //此时data改变并不会出发 updated beforeUpdate 两个钩子函数 因为mounted之后才会实时监控data变化 
    },
    beforeMount () { //开始挂载编译生成的html到对应的位置 此时还没有将编译好的html渲染到页面上 之后会创建$el属性

    },
    mounted(){ //此时已经有$el属性 页面已经完成渲染 可以在此时发送ajax请求 该钩子函数在生命周期中只执行一次
    
    },
    beforeUpdate () { //mounted执行的data数据监听 发生在虚拟 DOM 打补丁之前 可访问现有dom
      console.log('%c%s','color:green','beforeUpdate的data内容')
      console.log(this.$data)
      console.log(JSON.stringify(this.$data))
      console.log('%c%s','color:purple',"beforeUpdate更新前的dom内容")
      console.log(this.$el);
      console.log(this.$el.innerHTML)
    },
    updated(){ //数据更新后的状态 但最好不要在此做操作 而是用 watcher或者计算属性
      console.log('%c%s','color:green','beforeUpdate的data内容')
      console.log(this.$data)
      console.log(JSON.stringify(this.$data))
      console.log('%c%s','color:purple',"beforeUpdate更新前的dom内容")
      console.log(this.$el);
      console.log(this.$el.innerHTML)
    },
    beforeDestroy () { //vue实例销毁前的钩子函数
      
    },
    destroyed () { //vue实例销毁执行的钩子函数
      
    }



  }
</script>
<style>
</style>
