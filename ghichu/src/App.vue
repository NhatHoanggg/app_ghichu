<template>
  <div>
    ENTER NOTE
    <input type="text" v-model="currentNote">
    <button @click = "save">SAVE</button>
    <hr>
      List Note: 
    <div v-for = "(item, index) of list" :key = "index">
      <input type="checkbox" v-model="item.done">
      <span class = "{done: item.done}">
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
      //alert(this.currentNote);
      //this.list.push(this.currentNote)
      this.list.push({content: this.currentNote, done: false})
    }
  }
}
</script>

<style>
.done{
  /* text-decoration: line-through; */
  color: blue;
}
</style>
