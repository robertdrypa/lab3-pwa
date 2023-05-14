<template>
    <div class="thumb-wrapper">
        <img :src="item" v-for="(item,index) in images" :key="index" class="thumb" @click="sendImage(item)">
    </div>
</template>

<script>
export default {
  name: 'thumb',
  props: {
    images : {
        type: Array,
        default:()=>[]
    },

  },
  methods:{
        sendImage(url){
            this.$emit('selectedImg',url)
        }
    }
}
</script>

<style scoped>
.thumb-wrapper{
    display: flex;
    margin: auto;
    justify-content: center;
    padding-top: 20px;
}
.thumb{
  width: 100px;
  height: 100px;
  margin: 3px;
}

.thumb:hover{
    cursor: pointer;
    width: 105px;
    height: 105px;
}

</style>