<template>
    <div class="news">
        <div class="container">
            <div class="sectionTitle">最新消息</div>
            <div class="timeline-container">
                <!--  時間線 -->
                <div class="timeline">
                <!--  最新消息項目 -->
                    <div class="timeline-item" data-text="FATHER OF THE TURKS" v-for="data in news">
                        <div class="timeline__content">
                            <img class="timeline__img" :src="data.img"/>
                            <h2 class="timeline__content-title">{{ data.name }}</h2>
                            <p class="timeline__content-desc">{{ data.description }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { reactive } from 'vue';

const news = reactive([
    {
        img: 'http://i.cdn.ensonhaber.com/resimler/diger/ataturk_3473.jpg',
        name: '最新消息1',
        description: 'He was born in 1881 (probably in the spring) in Salonica, then an Ottoman city, now inGreece. His father Ali Riza, a customs official turned lumber merchant, died when Mustafawas still a boy. His mother Zubeyde, adevout and strong-willed woman, raised him and his sister.'
    },  {
        img: 'http://i.cdn.ensonhaber.com/resimler/diger/ataturk_3473.jpg',
        name: '最新消息2',
        description: 'He was born in 1881 (probably in the spring) in Salonica, then an Ottoman city, now inGreece. His father Ali Riza, a customs official turned lumber merchant, died when Mustafawas still a boy. His mother Zubeyde, adevout and strong-willed woman, raised him and his sister.'
    },  {
        img: 'http://i.cdn.ensonhaber.com/resimler/diger/ataturk_3473.jpg',
        name: '最新消息3',
        description: 'He was born in 1881 (probably in the spring) in Salonica, then an Ottoman city, now inGreece. His father Ali Riza, a customs official turned lumber merchant, died when Mustafawas still a boy. His mother Zubeyde, adevout and strong-willed woman, raised him and his sister.'
    }
]);


</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";
.sectionTitle {
    @include sectionTitle;
}
.news {
    @include tbp;
}

.timeline {
  display: flex;
  margin: 0 auto;
  flex-wrap: wrap;
  flex-direction: column;
//   max-width: 700px;
  position: relative;
  &__content {
    &-title {
      font-weight: normal;
      font-size: 2.5rem;
      margin: -10px 0 0 0;
      transition: .4s;
      padding: 1rem;
      box-sizing: border-box;
    }
    &-desc {
      margin: 0;
      font-size: 15px;
      box-sizing: border-box;
      font-weight: normal;
      line-height: 25px;
    }
  }
  &:before {
    position: absolute;
    left: 50%;
    width: 2px;
    height: 100%;
    margin-left: -1px;
    content: "";
    background: #000;
    // @include responsive() {
    //   left: 40px;
    // }
  }
  &-item {
    padding: 40px 0;
    // opacity: .3;
    // filter: blur(2px);
    transition: .5s;
    box-sizing: border-box;
    width: calc(50% - 40px);
    display: flex;
    position: relative;
    // transform: translateY(-80px);
    &:before {
      content: attr(data-text);
      letter-spacing: 3px;
      width: 100%;
      position: absolute;
      font-size: 13px;
      border-left: 2px solid rgba(#fff, .5);
      top: 70%;
      margin-top: -5px;
      padding-left: 15px;
      opacity: 0;
      right: calc(-100% - 56px);
    }
    &:nth-child(even) {
      align-self: flex-end;
      &:before {
        right: auto;
        text-align: right;
        left: calc(-100% - 56px);
        padding-left: 0;
        border-left: none;
        border-right: 2px solid rgba(#fff, .5);
        padding-right: 15px;
      }
    }
    &--active {
      opacity: 1;
      transform: translateY(0);
      filter: blur(0px);
      &:before {
        top: 50%;
        transition: .3s all .2s;
        opacity: 1;
      }
      .timeline__content-title {
        margin: -50px 0 20px 0;
      }
    }
    @include responsive() {
      align-self: baseline !important;
      width: 100%;
      padding: 0 30px 150px 80px;
      &:before {
        left: 10px !important;
        padding: 0 !important;
        top: 50px;
        text-align: center !important;
        width: 60px;
        border: none !important;
      }
      &:last-child {
        padding-bottom: 40px;
      }
    }
  }
  &__img {
    max-width: 100%;
    // box-shadow: 0 10px 15px rgba(0, 0, 0, .4);
  }
  &-container {
    width: 100%;
    position: relative;
    padding: 80px 0;
    transition: .3s ease 0s;
    background-attachment: fixed;
    background-size: cover;
    &:before {
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background: #fffff;
      content: "";
    }
  }
}

</style>