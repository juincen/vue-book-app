<template>
  <div id="app">
    
    {{ msg }}

    <p v-if="score>80">优秀</p>
    <p v-else>差劲</p>

    <ul >
      <li v-for="car in cars" :key="car">{{ car }}</li>
    </ul>

    <p>{{ inputValue }}</p>
    <p>{{ jisuan }}</p>
    <input type="text" v-model="inputValue" />

    <br />

    <button  @click="fun">按钮</button>

    <br />

    <input :value="inputValue" />

  </div>
</template>

<script>

export default {
  name: 'App',
  props:{

  },
  data(){
    return {
      msg:'HelloWorld',
      score:81,
      cars:[
        '奥迪',
        '宝马',
        '大众',
        '马自达',
        '奇瑞'
      ],
      inputValue:''
    }
  },
  watch: {
    inputValue(val){
      //val参数是最新的值
      console.log(val);
    }
  },
  computed:{
    jisuan(){
      return this.inputValue * 2;
    }
  },
  methods:{
    fun(){
      console.log('这是一个方法');
    }
  },
  mounted(){
    console.log(this);
  }

}
</script>

<style>

</style>
