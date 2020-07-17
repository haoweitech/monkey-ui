<template>
  <div>
    <m-row v-for="(v,k) in [
      {size:'large',text:'超大尺寸'},
      {size:'default',text:'默认尺寸'}, 
      {size:'small',text:'小尺寸'} ,
    ]"
    :key="k"
    :style="{marginBottom: '15px'}"><m-input :size="v.size" :placeholder="v.text" :style="{maxWidth: '200px'}"/></m-row>
    <span>{{v}}</span>
  </div>
</template>

<script>
import MInput from "@/components/monkey-ui/input/MInput"
import MRow from "@/components/monkey-ui/row/MRow"

export default {
  components: {
    MInput,
    MRow,
  },
  data() {
    return {
        v: 111
    }
  }
}
</script>

<style>

</style>
