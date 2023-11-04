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
                            <span class="timeline__content-date">{{ data.date }}</span>
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
        img: '/images/img_news_01.png',
        name: '世界貓咪日',
        date: '2023.02.02',
        description: '「一群貓貓的心願，便是建立一個人貓共存的社會。」為推廣人貓共存、幸福生活這個理念，我們特別舉辦首次「吸貓節」希望能藉著這一天，向每一個台灣人推廣愛貓的訊息!'
    },  {
        img: '/images/img_news_02.png',
        name: '貓咪健走趴',
        date: '2023.06.24',
        description: '鼓勵民眾養成良好運動習慣，並且帶著小孩、寵物出門踏青。活動地點鄰近動物園，參加者須穿著或配戴動物相關主題服飾、配件等，邀市民朋友踴躍報名並盛裝參與，只要扮裝符合主題並完成闖關，即可獲精美小禮及抽獎券，有機會把提鍋等大獎抱回家。'
    },  {
        img: '/images/img_news_03.png',
        name: '喵喵頌',
        date: '2023.08.09',
        description: '我們會邀請國際知名演奏家舉辦一場音樂會，所得票額全數捐給流浪動物相關單位。我們是一群熱愛音樂的人，因為音樂美好我們的生命，所以我們同樣也關懷周遭每個的生命，不只要讓牠們活著，還要活得更好，讓這些生命感受到愛，就如同我們對音樂的熱愛。你我一起貢獻手上的資源，讓生命更美好，讓世界充滿更多愛。'
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
    background: var(--gray_D4);
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
    padding: 3rem 0;
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