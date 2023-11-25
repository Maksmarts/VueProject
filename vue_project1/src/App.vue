<script > 
export default{
  data(){
    return{
      name:'',
      list:[],
    }
},
methods:{
  sayHello(){
    this.list.push(this.name);
    console.log(this.list);
    this.name='';
    document.getElementById('i').focus();
  },
  remove(item){
    const index = this.list.indexOf(item);
    this.list.splice(index, 1);
    console.log(this.list);
    document.getElementById('i').focus();
  }
}
}
</script>

<template>
  <div class="stiker">
    <div class="textbox">
      <h1>СПИСОК ДЕЛ </h1>
      <!-- {{ name==''?'_______' :name }} -->
      <p>Мой список</p>
      <hr>
      <input class="in" id="i" type="text" v-model="name" v-on:keypress.enter="sayHello"> 
      <button v-if="name==''" disabled>Введите задачу</button>
      <button v-else v-on:click="sayHello()" >Добавить в список</button>
    <h3>Задачи:</h3>
    <ul >
      <li v-for="item in list">
        <!-- <input type="checkbox" class="check" v-on:click=" remove()" v-on:change="doCheck(index, 'need')"/> -->
        <span v-on:click=" remove(item)">
      {{ 
      item
      }}
      </span>
      </li>
    </ul>
    </div>
    <div>
    <!-- <input type="checkbox" id="scales" name="scales" checked />
    <label for="scales">Scales</label> -->
  </div>
</div>
 
</template>

<style scoped>

</style>
