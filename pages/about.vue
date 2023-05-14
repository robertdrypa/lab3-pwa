<template>
    <div class="main-wrap">
        <h1 class="colorRed">About</h1>
        <div class="alert">
            <button @click="showInfo">Kliknij mnie</button>
        </div>
        <BigImage image="https://www.fotopolis.pl/i/images/9/5/7/dz0zODg4Jmg9NTE4NA==_src_181957-PA160006.JPG"/>
        <Thumb image1="https://www.fotopolis.pl/i/images/9/5/5/dz01MTg0Jmg9Mzg4OA==_src_181955-PA160002.JPG"
        image2="https://s3.eu-central-2.wasabisys.com/interfotowp/wp-media-folder-blog-interfoto-eu/wp-content/uploads/2021/07/wybrane.jpg"
        image3="https://www.optyczne.pl/upload2/204743_P2260014a.JPG"
        image4="https://astropolis.pl/uploads/monthly_2019_06/Sonia.jpg.a4a1b2cebf78e8f723f4b9135058b4cb.jpg"
        image5="https://pliki.optyczne.pl/CR5/sample/CR5_6126_iso400.JPG"
        image6="https://www.fotopolis.pl/i/images/9/2/0/dz0xMDAwJmg9NjY3_src_151920-DSC_0632.JPG"
        />
    </div>

</template>
<script>
import BigImage from '~/components/gallery/bigImage.vue';
import Thumb from '~/components/gallery/thumb.vue';
import TopNav from '~/components/TopNav.vue';
export default {
    name: "AboutPage",
    components: { TopNav, BigImage, Thumb },

    methods: {
        showInfo: () => alert('Witaj')
    }
}
</script>
<style scoped>
.colorRed{
    color: red;
    text-align: center;
}
.main-wrap{
    justify-content: center;
    flex-wrap: wrap;
}

.alert{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    padding-bottom: 10px;
}
</style>
