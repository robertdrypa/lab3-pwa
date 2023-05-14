<template>
    <div class="thumb-section">
        <img :src="item" v-for="(item,index) in images" :key="index" class="thumb" @click="sendImage(item)" v-on:click="setSelected()" v-bind:class="{selected: isSelected}">
    </div>
</template>

<script>
export default {
    name: 'thumbModal',
    props: {
        images: {
            type: Array,
            default: () => []
        },

    },
    data() {
        return {
            isSelected: false
        }

    },

    methods: {
        sendImage(url) {
            this.$emit('selectedImg', url);
        },
        setSelected: function () {
            this.isSelected = !this.isSelected;
        }
    }
}
</script>

<style scoped>
.thumb-section{
    display: block;
    margin-left:30px;
    margin-right: 30px;
    margin-top: auto;
    margin-bottom: auto;
    justify-content: center;
}

.thumb{
  width: 100px;
  height: 100px;
  margin: 10px;
}

.thumb:hover{
    cursor: pointer;
    width: 105px;
  height: 105px;
}



</style>