<template>
  <div class="home">
    <div> 
       <el-table 
       :data="professors">
           <el-table-column
            prop="university_major"
            label="学部学科"
           >
            <template scope="scope">
                <span v-if="scope.row.university_major===1">仏教学部禅学科</span>
                <span v-if="scope.row.university_major===2">文学部国文学科</span>
                <span v-if="scope.row.university_major===3">文学部地理学科</span>
                <span v-if="scope.row.university_major===4">文学部社会学科</span>
                <span v-if="scope.row.university_major===5">文学部英米文学科</span>
                <span v-if="scope.row.university_major===6">文学部歴史学科</span>
                <span v-if="scope.row.university_major===7">文学部心理学科</span>
                <span v-if="scope.row.university_major===8">経済学部経済学科</span>
                <span v-if="scope.row.university_major===9">経済学部商学科</span>
                <span v-if="scope.row.university_major===10">経済学部現代応用経済学科</span>
                <span v-if="scope.row.university_major===11">法学部法律学科</span>
                <span v-if="scope.row.university_major===12">法学部政治学科</span>
                <span v-if="scope.row.university_major===13">経営学部経営学科</span>
                <span v-if="scope.row.university_major===14">経営学部市場戦略学科</span>
                <span v-if="scope.row.university_major===15">医療健康科学部診療放射線技術科学学科</span>
                <span v-if="scope.row.university_major===16">グローバルメディアスタディーズ学部グローバルメディアスタディーズ学科</span>
            </template>
           </el-table-column>
           <el-table-column
            prop="name"
            label="教授名"
           >
           </el-table-column>
           <el-table-column
            prop="status"
            label="Status"
           >
            <template scope="scope">
                <span v-if="scope.row.status===1"><el-button type="primary">利用可</el-button></span>
                <span v-else-if="scope.row.status===2">退室中</span>
                <span v-else-if="scope.row.status===3">会議中</span>
            </template>
           </el-table-column>
           <el-table-column
            label="詳細"
           >
           <template scope="scope">
            <router-link 
            :to="`/show/${scope.row.id}`"
            >
                <el-button type="danger">詳細</el-button>
                </router-link>
            </template>
           </el-table-column>
        </el-table>      


    </div>
  </div>
</template>

<script>

export default {
    name: 'Index',
    data () {
      return {
        //   Get Data From Firebase
          professors : [
        {id:1, name:"道重信",university_major : 1,status:1},
        {id:2, name:"田中勇",university_major : 2,status:1},
        {id:3, name:"伊藤尚広",university_major : 7,status:1},
        {id:4, name:"山田隆",university_major : 4,status:1},
        {id:5, name:"織田信正",university_major : 5,status:3},
        {id:6, name:"武田震源",university_major : 7, status:1},
        {id:7, name:"原直樹",university_major : 16, status:1},
      ]
      }
    },
 
  methods:{
    
  }
  
}


</script>
