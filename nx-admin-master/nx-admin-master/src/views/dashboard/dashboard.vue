<template>
  <div class="app-container">
    <div class="video-container">
      <div style='width:100%;display: flex;' v-for="(item,rowIndex) in rows" :key="rowIndex">
          <div v-for='(item,colIndex) in cols' :span="item" :key="''+rowIndex+colIndex" @click="setCurrent(rowIndex,colIndex)" :style="item==8?'height:200px;width:33.3%;':item==12?'height:300px;width:50%;':'height:600px;width:100%;'">
            <div class="video-controller" :style="(rowIndex==currentIndex[0]&&colIndex==currentIndex[1])?'background-color: #5ea6f1':''" title='视频监控'>
              <video class="video"></video>
            </div>
          </div>
      </div>
    </div>
    <div style="display: flex;">
      <div class='splitClass' @click='splitVideo(1,1)' style='background-color: #ff7e23;'>1</div>
      <div class='splitClass' @click='splitVideo(2,2)' style='background-color: #00d8cb;'>4</div>
      <div class='splitClass' @click='splitVideo(3,3)' style='background-color: #681bb7;'>9</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VideoMonitor',
  data() {
    return {
      rows:[1],
      cols:[24],
      currentIndex:[0,0],
    }
  },
  methods: {
    splitVideo(row,col) {
      this.rows=[];
      this.cols=[];
      for(let i=0;i<row;i++){
        this.rows.push(1);
      }
      for(let i=0;i<col;i++){
        this.cols.push(24/col);
      }
    },
    setCurrent(row,col){
      this.currentIndex=[row,col];
    },
  }
}
</script>


<style>
.video-container{

}

.splitClass {
  cursor: pointer;
  color: white;
  width: 30px;
  height: 30px;
  text-align: center;
  line-height: 30px;
}
 
.video {
  border: 1px solid #fff;
  margin-bottom:5px;
}

.video:hover {
  border: 3px solid red;
}

.video-controller{
  height:100%;
}
 
.panel {
  float: left;
}
 
video {
  object-fit: fill;
  width: 100%;
  height: 100%;
  background-color: black;
}
 
video::-webkit-media-controls-enclosure {
  display: none !important;
}
 
video::-webkit-media-controls {
  display: none !important;
}
 
.selected {
  background-color: red;
}

 
 
 
</style>
