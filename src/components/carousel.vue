<template>
    <div id="carouselExampleCaptions" class="carousel slide">
        <!-- dot -->
        <div class="carousel-indicators">
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
        </div>
        <!-- 內容 -->
        <div class="carousel-inner">
            <div class="carousel-item" v-for="data in carouselData" v-bind:class="{ active: data.active }">
                <img :src="data.img" class="d-block w-100" :alt="data.name">
                <div class="carousel-caption d-md-block text-carousel">
                    <h3>{{ data.name }}</h3>
                    <div class="info">{{ data.description }}</div>
                </div>
            </div>
        </div>
        <!-- 左右切換的按鈕 -->
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
        </button>
    </div>
</template>

<script setup>
import { reactive } from 'vue';

const carouselData = reactive([
    {
        img: '/images/img_carousel_01.png',
        name: '蛋蛋昨天還在的｜社區免費結紮服務站',
        description: `2023年10月10日，我們在市民廣場舉辦了貓咪社區免費結紮活動。活動當天，共有 50 名貓咪接受了免費結紮手術。競選部表示，此次活動是對社區流浪貓咪的一次關愛，希望通過活動，讓更多流浪貓咪得到妥善安置，減少流浪貓咪對環境的影響。
            
            #關注流浪動物保護 #減少流浪動物數量 #讓流浪動物得到妥善安置`,
        active: true
    },  {
        img: '/images/img_carousel_02.png',
        name: '過去是 7 秒，過不去是 7 天｜交通法規課程',
        description: `2023年11月1日，競選部在市民廣場舉辦了貓咪外出交通安全課程。活動當天，共有 99 名飼主參加了課程。競選部表示，貓咪外出時，如果沒有使用牽繩，很容易發生車禍。因此，飼主在帶貓咪外出時，一定要使用牽繩，並注意交通安全。
                
            #外出一定要使用牽繩 #注意交通安全`,
        active: false
    },  {
        img: '/images/img_carousel_03.png',
        name: '找到溫暖的家｜關懷送養會',
        description: `2023年11月3日，競選部在競選部門口舉辦了貓咪送養會。活動由競選部發起，台光黨協辦。活動旨在減少流浪貓咪數量，讓流浪貓咪獲得更好的照護。活動當天，共有 87 名貓咪找到了新家。競選部表示，此次活動是對流浪動物的一次關愛，希望通過活動，讓更多流浪動物找到溫暖的家。

            #關注動物保護 #減少流浪動物數量 #妥善安置`,
        active: false
    }
]);

</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";
.text-carousel {
    background-origin: padding-box;
    color: var(--black);
    background-color: var(--white);
    padding: 3rem;
    position: absolute;
    bottom: 0;
    .info {
        white-space: pre-line;
        text-align:justify;
    }
} 
.carousel-inner {
    border-radius: 0.5rem;
}
.carousel-indicators button {
    background-color: var(--primary);
}
.text-carousel {
    @include media-breakpoint-up(1200px) {
        position: relative;
        left: 0;
        padding: 2rem;
    }
}

</style>