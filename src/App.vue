<template>
<div class="app">
 <h1 v-text="title"></h1>
<input v-model="newItem" @keyup.enter="addNew">
 <ul>
   <li v-for="item in items" v-bind:class="{fininshed:item.isFinished}" v-on:click="toggleFinish(item)">
     {{item.lable}}
   </li>
 </ul>
  <p>childen tell me :{{childenwords}}</p>
  <br>
  <p>childen tell me :{{childenwords1}}</p>
 <Component-a msgfromfather="hello sonA" v-on:childen-tell-me-sth='listentoson'><Component-a>
 <Component-b msgfromfather="hello sonB" v-on:childen-tell-me-sth='listentoson'><Component-b>
 </div>
</template>

<script>
import Hello from './components/Hello'
import ComponentA from './components/ComponentA'
import ComponentB from './components/ComponentB'
import Store from './Store'

export default {
//export  {
  components: {
    Hello,
<<<<<<< HEAD
    Store,
    ComponentB,
    ComponentA
    },
=======
    Store
  },
>>>>>>> 3c5b2bea9d93986c08b0fb550188a9fe8e180205

  data(){
    return {
      title:"this is a todo list",
      items:Store.fetch(),
/*      [
          {
            lable:'coding',
            isFinished:false
          },
          {
            lable:'wolking',
            isFinished:true

          }
      ]
 */
<<<<<<< HEAD

      newItem:"",
      childenwords:"",
      childenwords1:""
=======
      
      newItem:""
>>>>>>> 3c5b2bea9d93986c08b0fb550188a9fe8e180205
    }
  },

  methods:{
//        toggleFinish:function(item){
    toggleFinish(item){
      //console.log(item)
      //console.log(item.isFinished=!item.isFinished)
      item.isFinished=!item.isFinished
      },

    addNew(){
      console.log(this.newItem)
      console.log(this.items)
      this.items.push({
        lable:this.newItem,
        isFinished:false
      })
      this.newItem = ""
    },

    listentoson(msg){
      console.log(msg)
      this.childenwords=msg,
      this.childenwords1=msg
    }
  },

  watch:{
    items:{
      handler:function(items){
        //console.log(val,oldval),
        Store.save(items)
      },
      deep:true
    }
  }
}
</script>

<style>
.fininshed{
  text-decoration:underline;
}
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
