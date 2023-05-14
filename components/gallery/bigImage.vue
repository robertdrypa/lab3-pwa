<template>
    <div class="bigImg">
    <img :src="image" class="img" @click="showModal">
</div>
</template>

<script>
export default {
  name: 'BigImage',
  props: {
    image : {
        type: String,
        default: () => ''
    }
  },
  methods: {
    showModal() {
      this.$emit('rm', true)
    }
  }
}
</script>

<style>
.bigImg{
  display:flex;
  justify-content: center;
}

.img{
  width: 600px;
  height:400px;
  cursor:pointer;
}

</style>