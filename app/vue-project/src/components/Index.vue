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
            label="Status"
           >
            <el-button type="danger">詳細</el-button>
           </el-table-column>
        </el-table>      
    </div>
  </div>
</template>

<script>

export default {
    name: 'Index',
    props: {
        'professors':{
            type: Array,
            required: true
        }
    },
    data () {
      return {
          
      }
    },
 
  methods:{
    
  }
  
}


</script>
