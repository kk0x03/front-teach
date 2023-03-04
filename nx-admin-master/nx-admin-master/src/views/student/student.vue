<template>
  <div class="info-body">
    <div class="student-container">
      <div class="student-infotmation" v-for="item in list" :key="item">
        <div class="student-div">
          <div class="student-pic"><img class="pic" :src="item.pic"></div>
          <div class="student-name">姓名:{{item.name}}</div>
          <div>证件:{{item.zhenjian}}</div>
          <div>电脑编号:{{item.bianhao}}</div>
          <div>是否违规:{{item.flag1}}</div>
        </div>
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'student',
  data() {
    return {
      list:[
        {
          name:"1",pic:"null",zhenjian:"zhenjian1",bianhao:"bianhao1",flag1:"1"
        },
        {
          name:"2",pic:"null",zhenjian:"zhenjian2",bianhao:"bianhao2",flag1:"2"
        }
      ]
    }
  },
  methods: {
  }
}
</script>


<style>
.student-container{
  display: flex;
  padding-top: 40px
}

.student-infotmation{
  width:50%;
}

.student-div{
  width: 50%;
  margin: auto;
  font-size: 16px;
  font-family: auto;
  font-weight: bold;
  text-align: center;
}

.student-pic{
  height: 400px;
  border: 1px solid #42b983;
  border-radius: 15px;
}

.pic{
  width:100%;
  height:100%;
  border-radius: 15px;
}


</style>
