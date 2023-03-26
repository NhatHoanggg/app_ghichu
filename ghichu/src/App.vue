<template>
  <div class = "container">
    <div class="header">
      <div>
        ENTER TASKS
        <input class = "input-box" type="text" v-model="currentNote" placeholder="Input tasks here..">
        <button class = "btn" @click = "save">SAVE</button>
      </div>
      you are typing: {{currentNote}}
    <hr>
      List Note: 
    </div>
    <div v-for = "(item, index) of list" :key = "index" class = "item">
      <input type="checkbox" v-model="item.done" >
      <span class = "content" v-bind:class = "{done: item.done}" >
        {{ item.content }} 
      </span>
    </div>
  </div>
</template>

<script>

export default {
  data(){
    return{
      currentNote: "",
      list : [
        {content: 'ngu', done: false},
        {content: 'an', done: false},
        {content: 'di choi', done: false},
        {content: 'hoc bai', done: false},
        {content: 'xem phim', done: false},
      ],
    }
  },
  mounted(){

  },
  computed: {

  },

  methods:{
    save(){
      this.list.push({content: this.currentNote, done: false})
    }
  }
}
</script>

<style>
*{
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.done{
  text-decoration: line-through;
}

.container{
  width: 100%;
  height: 1000px;
  font-size: 30px;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  
}

.header{
  text-align: center;
}

.input-box{
  font-size: 30px;
  margin-left: 30px;
}

.btn{
  font-size: 30px;
  margin-left: 30px;
}

.content{
  margin-left: 15px;
}

.item{
  width: 800px;
  padding: 15px;
  margin: 0 ;
  margin-left: 15px;
  border: 1px solid #ddd; 
  background-color: #f6f6f6; 
  font-size: 30px; 
  color: black; 
  display: block;
  transform: translateX(40%);
}

.item:hover{
  background-color: #eee;
  font-size: larger;
  padding-top: 30px;
  padding-bottom: 30px;
}

</style>

