<template>
  <div class="home">
    <Index :professors=professors />
  </div>
</template>
<script>
// @ is an alias to /src
import Index from '@/components/Index.vue'

export default {
  components: {
    Index
  },
  data () {
    return {
      professors : [
        {id:0, name:"矢野大樹",university_major : 1,status:0},
        {id:1, name:"田中勇",university_major : 2,status:1},
        {id:2, name:"伊藤尚広",university_major : 7, status:1},
        {id:2, name:"山田隆",university_major : 4, status:1},
        {id:2, name:"織田信正",university_major : 5, status:1},
        {id:2, name:"武田震源",university_major : 7, status:1},
        {id:2, name:"原直樹",university_major : 16, status:1},
      ]
    }
  },
  methods:{
    
  }
  
}


</script>
