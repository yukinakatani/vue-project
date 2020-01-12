<template>
  <div class="home">
   ID:{{professor.id}}
   教授名:{{professor.name}}
   学部:{{professor.university_major}}
  </div>
</template>
<script>
/* eslint-disable no-console */


export default {
  components: {
   
  },
  data () {
    return {
        professors : [
        {id:1, name:"道重信",university_major : 1,status:1},
        {id:2, name:"田中勇",university_major : 2,status:1},
        {id:3, name:"伊藤尚広",university_major : 7,status:1},
        {id:4, name:"山田隆",university_major : 4,status:1},
        {id:5, name:"織田信正",university_major : 5,status:3},
        {id:6, name:"武田震源",university_major : 7, status:1},
        {id:7, name:"原直樹",university_major : 16, status:1},
      ],
      professor : []    
    }
  },
  mounted () {
      this.getUserDetail()
  },
  methods:{
    getUserDetail () {
      const dataId = parseInt(this.$route.params.id,10);
      const data = this.professors.find(professor => (
        professor.id === dataId
        
      ));
      this.professor = data;   
      console.log(this.professor);
    }   
  }
  
}


</script>
