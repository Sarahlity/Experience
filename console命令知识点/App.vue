<template>
<div >
  <el-button type="primary" @click="aaa" >1234</el-button>
{{time}}
</div>
</template>

<script>
  export default {
    data() {
      return {
        time:"wevdsffd",
          items:[
        {name:"达拉斯",value:'123'},
        {name:"休斯顿",value:'455'}
          ]
      }
    },
    methods:{
      aaa(){
     this.time="12345678"
      }
    },
    created(){ 

    },
    mounted(){ 
    console.time("test-demo");
    const str1 = "hello";
    const str2 = "world";
    console.log(str1, str2);
    console.table(this.items)//打印出的数组对象数据在控制台是表格结构
    console.log("%c%s","color:pink","打印的内容是粉色的")//console.log 可以打印带样式的文字 还有图片等等
    var a=1200;
    for(var i=0;i<a;i++){

    }
    console.timeEnd("test-demo"); //这个console.time 和console.timeEnd方法 必须传入相同参数 这个对测试同步的代码执行时间有帮助
    console.log(Promise)//网上说log和dir没有太大区别 但是在现在的谷歌里 打印函数 log只是打印一个范范的函数 有种string化的感觉
    console.dir(Promise)//而dir会打印这个函数的具体属性 方法等等....
    },
  }
</script>
<style>
</style>
