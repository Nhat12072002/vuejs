<script>
import Mixin from './mixin'
export default{
  mixins : [Mixin]

}
</script>
<template>
  <div id="test">
    <h1>Đây là kết quả: {{ this.count }}</h1><br>
    <button @click="increment()">Tăng</button>
  </div>
</template>



<style scoped>
 #test{
  background-color: #4CAF50;
    color: white;
    padding: 100px;
}

</style>
