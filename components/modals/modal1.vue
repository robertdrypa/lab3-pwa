<template>
    <div class="modal">
        <div class="modal-view">
            <thumbInModal :images="items" @selectedImg="showImage($event)"/>
            <div class="main-img-wrapper" >
                <img class="main-img" :src="image">
            </div>
            <div class="closingBtn">
            <button @click="closeModal">Close</button>
            </div>
        </div>
    </div>
</template>

<script>
import thumbInModal from '../gallery/thumbInModal.vue';
export default{
    name: "Modal",
    props: {
        image: {
            type: String,
            default: () => ""
        }
    },
    methods: {
        closeModal() {
            this.$emit("close", false);
        },
        showImage(url) {
            this.image = url;
        }
    },
    data() {
        return {
            items: [
            'https://www.fotopolis.pl/i/images/9/5/7/dz0zODg4Jmg9NTE4NA==_src_181957-PA160006.JPG',
            'https://www.fotopolis.pl/i/images/9/5/5/dz01MTg0Jmg9Mzg4OA==_src_181955-PA160002.JPG',
            'https://s3.eu-central-2.wasabisys.com/interfotowp/wp-media-folder-blog-interfoto-eu/wp-content/uploads/2021/07/wybrane.jpg',
            'https://www.optyczne.pl/upload2/204743_P2260014a.JPG',
            'https://astropolis.pl/uploads/monthly_2019_06/Sonia.jpg.a4a1b2cebf78e8f723f4b9135058b4cb.jpg',
            'https://pliki.optyczne.pl/CR5/sample/CR5_6126_iso400.JPG'
            ],
        };
    },
    components: { thumbInModal }
}
</script>
<style scoped>
.modal{
    display:flex;
    justify-content: center;
    position:absolute;
    top:0;
    left:0;
    width: 100vw;
    height: 100vh;
    background: rgba(55, 55, 55, 0.675);
}

.modal-view{
    background-color: white;
    width:800px;
    height: 600px;
    display: flex;
    flex-direction: row;
    position: absolute;
    top: 10vh;
    border: 0.5px solid darkgray;
}

.main-img{
    width:400px;
    height:400px;
}

.main-img-wrapper{
    margin:auto;
}

button{
    background-color: darkgray;
    color:white;
    border-radius: 7px;
    border: none;
    font-size:larger;
    margin: 5px;
}

button:hover{
    cursor:pointer;
}

.selected{
    border: 1px solid black
}
</style>
