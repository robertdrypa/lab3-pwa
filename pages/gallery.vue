<template>
    <div class="main-wrap">
        <div class="gallery-wrap">
        <BigImage :image="bigImg" @rm="runModal($event)"/>
        <Thumb :images="items" @selectedImg="showImage($event)"/>
        <Modal1 v-show="showModal" :image="bigImg" @close="runModal($event)"/>
        </div>
    </div>

</template>
<script>
import BigImage from '~/components/gallery/bigImage.vue';
import Thumb from '~/components/gallery/thumb.vue';
import Modal1 from '~/components/modals/modal1.vue';
import TopNav from '~/components/TopNav.vue';

export default {
    name: 'Gallery',
    components: { TopNav, BigImage, Thumb, Modal1 },
    data(){
        return{
            items:[
                'https://www.fotopolis.pl/i/images/9/5/7/dz0zODg4Jmg9NTE4NA==_src_181957-PA160006.JPG',
                'https://www.fotopolis.pl/i/images/9/5/5/dz01MTg0Jmg9Mzg4OA==_src_181955-PA160002.JPG',
                'https://s3.eu-central-2.wasabisys.com/interfotowp/wp-media-folder-blog-interfoto-eu/wp-content/uploads/2021/07/wybrane.jpg',
                'https://www.optyczne.pl/upload2/204743_P2260014a.JPG',
                'https://astropolis.pl/uploads/monthly_2019_06/Sonia.jpg.a4a1b2cebf78e8f723f4b9135058b4cb.jpg',
                'https://pliki.optyczne.pl/CR5/sample/CR5_6126_iso400.JPG'

            ],
          bigImg:'https://www.swiatobrazu.pl/zdjecie/artykuly/311407/iphone-5-przykladowe-zdjecia-4.jpeg',
            showModal : false

        }
    },
    methods: {
        showImage(url) {
            this.bigImg = url
        },
        runModal(e){
            this.showModal = e
        }
    }

}
</script>
<style scoped>
.main-wrap{
    justify-content: center;
    flex-wrap: wrap;

}

.gallery-wrap{
    margin-top: 20px;
}

</style>
