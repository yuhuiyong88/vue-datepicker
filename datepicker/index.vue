<template>
    <date-picker v-model="startTime"></date-picker>
</template>

<script>
//cnpm install moment --save-dev
//cnpm install vue2-datepicker --save-dev

import DatePicker from 'vue2-datepicker'
import moment from 'moment';

export default {
  data: function () {
        return {
            startTime: "", 
        }
    },
  watch:{  
      startTime:function(newval,oldval){  
          this.startTime=moment(newval).format("YYYY-MM-DD");
          //执行的事件
      },  
      endTime:function(newval,oldval){  
          this.endTime=moment(newval).format("YYYY-MM-DD");
          //执行的事件
      }  
  },
  mounted: function(){
      var current = moment();
      this.startTime = current.format('YYYY-01-01');
      this.endTime = current.format('YYYY-MM-DD');
  },
  components: {
      DatePicker: DatePicker
  }
}
  
</script>


<style scoped>

</style>
