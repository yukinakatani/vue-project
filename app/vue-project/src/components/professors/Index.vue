<template>
  <div class="home">
    <div> 
      <el-table :data="professors">
        <el-table-column
          prop="university_major"
          label="学部学科"
        >
          <template scope="scope">
            <span v-if="scope.row.university_major===1">仏教学部禅学科</span>
            <span v-else-if="scope.row.university_major===2">文学部国文学科</span>
            <span v-else-if="scope.row.university_major===3">文学部地理学科</span>
            <span v-else-if="scope.row.university_major===4">文学部社会学科</span>
            <span v-else-if="scope.row.university_major===5">文学部英米文学科</span>
            <span v-else-if="scope.row.university_major===6">文学部歴史学科</span>
            <span v-else-if="scope.row.university_major===7">文学部心理学科</span>
            <span v-else-if="scope.row.university_major===8">経済学部経済学科</span>
            <span v-else-if="scope.row.university_major===9">経済学部商学科</span>
            <span v-else-if="scope.row.university_major===10">経済学部現代応用経済学科</span>
            <span v-else-if="scope.row.university_major===11">法学部法律学科</span>
            <span v-else-if="scope.row.university_major===12">法学部政治学科</span>
            <span v-else-if="scope.row.university_major===13">経営学部経営学科</span>
            <span v-else-if="scope.row.university_major===14">経営学部市場戦略学科</span>
            <span v-else-if="scope.row.university_major===15">医療健康科学部診療放射線技術科学学科</span>
            <span v-else-if="scope.row.university_major===16">グローバルメディアスタディーズ学部グローバルメディアスタディーズ学科</span>
          </template>
        </el-table-column>
        <el-table-column
          prop="name"
          label="教授名"
        >
        </el-table-column>
        <el-table-column prop="status" label="Status">
          <template scope="scope">
            <span v-if="scope.row.status===1"><el-tag>利用可</el-tag></span>
            <span v-else-if="scope.row.status===2"><el-tag type="info">退室中</el-tag></span>
            <span v-else-if="scope.row.status===3"><el-tag type="danger">会議中</el-tag></span>
          </template>
        </el-table-column>         
        <el-table-column>
          <template scope="scope">
            <el-button type="success" :data="professors" plain @click="getProfessorDetail(scope.row.id); dialogVisible=true">More...</el-button>
          </template>
        </el-table-column>
      </el-table> 
      <!-- Modal   -->
      <el-dialog
        title="Status"
        :visible.sync="dialogVisible"
        width="90%"
        top="8vh"
        custom-class="modal"
      >   

  <!-- PC -->
        <!-- <span slot="footer" class="dialog-footer"> -->
        <el-row class="dialog-left-height hidden-sm-and-down">
          <el-col :xs="24" :sm="24" :md="12" :lg="12" class="dialog-left">
              <!-- v-bind:class="[professor.status===2 ? 'hey' : '']" -->
              <i v-if="professor.status===1" style="font-size: 200px;" class="el-icon-user"></i>
              <span v-if="professor.status===1">利用可</span>
              <span v-else-if="professor.status===2">退室中</span>
              <span v-else-if="professor.status===3">会議中</span> 
              
              {{professor.name}}
              <span v-if="professor.university_major===1">仏教学部禅学科</span>
              <span v-else-if="professor.university_major===2">文学部国文学科</span>
              <span v-else-if="professor.university_major===3">文学部地理学科</span>
              <span v-else-if="professor.university_major===4">文学部社会学科</span>
              <span v-else-if="professor.university_major===5">文学部英米文学科</span>
              <span v-else-if="professor.university_major===6">文学部歴史学科</span>
              <span v-else-if="professor.university_major===7">文学部心理学科</span>
              <span v-else-if="professor.university_major===8">経済学部経済学科</span>
              <span v-else-if="professor.university_major===9">経済学部商学科</span>
              <span v-else-if="professor.university_major===10">経済学部現代応用経済学科</span>
              <span v-else-if="professor.university_major===11">法学部法律学科</span>
              <span v-else-if="professor.university_major===12">法学部政治学科</span>
              <span v-else-if="professor.university_major===13">経営学部経営学科</span>
              <span v-else-if="professor.university_major===14">経営学部市場戦略学科</span>
              <span v-else-if="professor.university_major===15">医療健康科学部診療放射線技術科学学科</span>
              <span v-else-if="professor.university_major===16">グローバルメディアスタディーズ学部グローバルメディアスタディーズ学科</span>        
          </el-col>
          <el-col :xs="24" :sm="24" :md="12" :lg="12">
            {{time}}
            {{dayOfWeek}}
            {{month}}
            {{date}}th
          </el-col>
        </el-row>

<!-- スマホ -->
        <el-row class="hidden-md-and-up dialog-left-height-sm">
          <el-col :xs="24" :sm="24">
              <!-- v-bind:class="[professor.status===2 ? 'hey' : '']" -->
              <span v-if="professor.status===1"><el-tag>利用可</el-tag></span>
              <span v-else-if="professor.status===2"><el-tag type="info">退室中</el-tag></span>
              <span v-else-if="professor.status===3"><el-tag type="danger">会議中</el-tag></span> 
                {{professor.name}}
              <span v-if="professor.university_major===1">仏教学部禅学科</span>
              <span v-else-if="professor.university_major===2">文学部国文学科</span>
              <span v-else-if="professor.university_major===3">文学部地理学科</span>
              <span v-else-if="professor.university_major===4">文学部社会学科</span>
              <span v-else-if="professor.university_major===5">文学部英米文学科</span>
              <span v-else-if="professor.university_major===6">文学部歴史学科</span>
              <span v-else-if="professor.university_major===7">文学部心理学科</span>
              <span v-else-if="professor.university_major===8">経済学部経済学科</span>
              <span v-else-if="professor.university_major===9">経済学部商学科</span>
              <span v-else-if="professor.university_major===10">経済学部現代応用経済学科</span>
              <span v-else-if="professor.university_major===11">法学部法律学科</span>
              <span v-else-if="professor.university_major===12">法学部政治学科</span>
              <span v-else-if="professor.university_major===13">経営学部経営学科</span>
              <span v-else-if="professor.university_major===14">経営学部市場戦略学科</span>
              <span v-else-if="professor.university_major===15">医療健康科学部診療放射線技術科学学科</span>
              <span v-else-if="professor.university_major===16">グローバルメディアスタディーズ学部グローバルメディアスタディーズ学科</span>        
          </el-col>
        </el-row>
        <el-row class="hidden-md-and-up dialog-left-height-sm">
          <el-col :xs="24" :sm="24">
            {{time}}
            {{dayOfWeek}}
            {{month}}
            {{date}}th
          </el-col>
        </el-row>
      </el-dialog>
    </div>
  </div>
</template>

<script>

/* eslint-disable no-console */

export default {
    name: 'Index',
    data () {
      return {
        //   Get Data From Firebase
          professors : [
        {id:1, name:"道重信",university_major : 1,status:2},
        {id:2, name:"田中勇",university_major : 2,status:1},
        {id:3, name:"伊藤尚広",university_major : 7,status:2},
        {id:4, name:"山田隆",university_major : 4,status:1},
        {id:5, name:"織田信正",university_major : 5,status:3},
        {id:6, name:"武田震源",university_major : 7, status:1},
        {id:7, name:"原直樹",university_major : 16, status:2},
      ],
      professor : [],
      time : "",
      dayOfWeek : "" ,
      month : "",
      date : "",
      dialogVisible : false
     
      }
    },
    methods:{
      getProfessorDetail(id){
        const dataId = parseInt(id,10);
        const data = this.professors.find(professor => (
          professor.id === dataId  
        ));
        this.professor = data; 
      },
      getNow () {
      const today = new Date();
      this.time = ("0"+today.getHours()).slice(-2) + ":" + ("0"+today.getMinutes()).slice(-2);
      this.date = today.getDate();
      const date = today.getDay();
      this.dayOfWeek = [ "Sun,", "Mon,", "Tue,", "Wen,", "Thur,", "Fry,", "Sat," ][date];
      const month = today.getMonth();
      this.month = ['Jan','Feb','Mar','Apr','May','June','July','Aug','Sept','Oct','Nov','Dec'][month];
    } 
    },
    mounted () {
      this.getNow()
  },
  
}
</script>

<style lang="scss">

$xl: 1920px; 
$lg: 1200px;
$md: 992px; 
$sm: 768px; 



.modal{
  height:85%;
}


.el-dialog__headerbtn {
  z-index: 10;
}

.el-dialog__body {
  height:100%;
  position: relative;
  top: -84px;
    .dialog-left-height-sm{
      height:50%;
    }
    .dialog-left-height {
      height:100%;
        .dialog-left {
          background-color:#F56C6C;
          height:100%;
          position: relative;
          left: -20px;
        } 
    }
}



</style>

