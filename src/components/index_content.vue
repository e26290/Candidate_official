<template>
    <div class="about tbp">
        <div class="about_img"></div>
        <div class="basic_info">
            <span class="sectitle">身段最軟 Ｑ 的立委候選人</span>
            <h2 class="name">吉吉語娜<span class="enName">CHICHI & YUNA</span></h2>
        </div>
    
        <div class="about_info">
            <div class="about_box">
                <!-- <span class="slogan">slogan</span> -->
                <p>
                各位鄉親父老大家好，我是立發委員候選人 語娜，副手 吉吉。
                <br/>
                我從小就養貓，對貓有著深厚的感情。我一直希望能夠為貓的權益發展做出貢獻，所以我決定參選立法委員。
                <br/>
                我有著豐富的鏟屎經驗，在處理各類貓咪問題方面有著獨到的見解。同時我也是一名狗派人士，曾經多次偷偷喂巷口的那條小黃。我相信，我的專業知識和熱心服務精神，能夠為廣大的貓市民、狗市民帶來切實的利益。
                <br/>
                我的副手是吉吉，今年 5 歲，是一個賓士貓。他是一名有著創新精神的貓青年，在摸爬打滾的領域具有深厚的造詣。他也是一名有責任感的團隊合作者，總是願意為他貓付出。我相信，他的專業能力和團隊合作精神，能夠為我的政見落地提供強有力的支持。
                <br/>
                我和吉吉都是這個國家的一份子，我們希望能夠用我們的努力，讓這座國家變得更加美好。我們誠摯地邀請您，投下您寶貴的一票，支持我們。
                </p>
            </div>
        </div>
    </div>

    <timeline />

    <div class="activity tbp">
        <div class="container">
            <div class="sectionTitle">展開行動</div>
            <div class="row">
                <div class="col-md-8">
                    <!-- TODO 圖片輪播 -->
                </div>
                <div class="activity_info">
                    <h6>小標題</h6>
                    <h1>大標題</h1>
                </div>
            </div>
            <h4>目前我們已經達成 ...</h4>
            <div class="row goal">
                <div class="col-md-2 card_goal" v-for="data in goal">
                    <span class="number">{{ data.number }}</span>
                    <span class="name">{{ data.name }}</span>
                </div>
            </div>
        </div>
    </div>

    <div class="policy tbp">
        <div class="container">
            <div class="sectionTitle">政策議題</div>
            <div class="row">
                <div class="col-md-4" v-for="data in policies">
                    <div class="card_policy">
                        <img :src="data.img" alt="政策一">
                        <div class="policy_info">
                            <div class="info">
                                <h3>{{ data.name }}</h3>
                                <p>{{ data.description }}</p>
                            </div>
                            <i class="fa-solid fa-angle-right fa-2x"></i>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        
    </div>

    <div class="goForm tbp">
        <div class="container">
            <div class="row d-flex justify-content-end">
                <div class="col-md-6">
                    <button>留言給我們！</button>
                </div>
            </div>
        </div>
    </div>

    <div class="donate tbp">
        <div class="container">
            <div class="row d-flex justify-content-end">
                <div class="col-md-6 content">
                    <span>因為您，更多弱勢貓貓得到幫助</span>
                    <!-- TODO 這邊要查一下資料怎麼做選項的切換內容 -->
                    <!-- 選項 -->
                    <div class="donateRadio">
                        <label for="">
                            <input type="radio">單筆捐款
                        </label>
                        <label for="">
                            <input type="radio">定期捐款
                        </label>
                    </div>
                    

                    <!-- 單筆選項 -->
                    <div class="onlyDonate">
                        <button>$ 300</button>
                        <button>$ 600</button>
                        <button>$ 1,200</button>
                        <button>自訂金額</button>
                    </div>
                    
                    <!-- 定期選項 -->
                    <div class="moonDonate">
                        <button>$ 300 / 月</button>
                        <button>$ 600 / 月</button>
                        <button>$ 1,200 / 月</button>
                        <button>自訂每月金額</button>
                    </div>

                    <!-- TODO 這個按鈕按下去會跳頁到小額捐款頁面 -->
                    <button>馬上捐款！</button>
                </div>
            </div>
        </div>
        
        
    </div>
</template>

<script setup>
import timeline from './timeline.vue';
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

const goal = reactive([
    {
        number: '45',
        name: '活動場次'
    },{
        number: '100H',
        name: '活動時數'
    },{
        number: '300K',
        name: '參與人次'
    }
]);

const policies = reactive([
    {
        name: '政策議題一',
        description: '政策議題內容一',
        img: 'https://images.unsplash.com/photo-1697799759368-2853eed5af65?auto=format&fit=crop&q=80&w=2587&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB'
    },{
        name: '政策議題二',
        description: '政策議題內容二',
        img: 'https://images.unsplash.com/photo-1697799759368-2853eed5af65?auto=format&fit=crop&q=80&w=2587&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVuf'
    },{
        name: '政策議題三',
        description: '政策議題內容三',
        img: 'https://images.unsplash.com/photo-1697799759368-2853eed5af65?auto=format&fit=crop&q=80&w=2587&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGV'
    }
]);
</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";

// 共用的樣式
.sectionTitle {
    @include sectionTitle;
}

.tbp {
    @include tbp;
}
// ------------------------------------------------------------------------

.about {
    position: relative;
    background-color: var(--gray_F3);
    .about_img {
        width: 100%;
        height: 600px;
        background-image: url(/images/img_about.png);
        background-position: top;
        background-size: cover;
        background-repeat: no-repeat;
    }
    .basic_info {
        background-color: var(--black);
        color: var(--white);
        max-width: 60%;
        padding: 2.5rem;
        padding-bottom: 3.5rem;
        @include flex($a:end);
        flex-direction: column;
        position: relative;
        top: -3rem;
        span, h2 {
            width: 45%;
            text-align: left;
        }
        .enName {
            font-size: 1rem;
            margin-left: 0.5rem;
        }
    }
    .about_info {
        @include flex($j:end);
        position: relative;
        top: -5rem;
        .about_box {
            background-color: var(--white);
            max-width: 70%;
            padding: 2.5rem;
            @include flex($a: end);
            flex-direction: column;
        }
        span, p {
            width: 100%;
            text-align: left;
        }
        .slogan {
            font-size: 3rem;
        }
        p {
            font-size: 1.25rem;
            line-height: 150%;
        }

    }
}
.activity {
    .goal {
        justify-content: center;
    }
    .card_goal {
        @include flex($g:0.2rem);
        flex-direction: column;
    }
    .number {
        font-size: 3.5rem;
    }
}
.policy {
    .card_policy {
        width: min(400px, 100%);
        aspect-ratio: 1/1;
        overflow: hidden;
        position: relative;
    }
    img {
        width: 100%;
    }
    .policy_info {
        @include flex;
        width: 90%;
        background-color: #ccc;
        padding: 1rem;
        position: absolute;
        left: 0;
        bottom: 0;
        .info {
            flex-basis: 100%;
            text-align: left;
        }
    }
}
.goForm {

}
.donate {
    // background-image: url();
    background-color: #ccc;
    .content {
        @include flex;
        flex-direction: column;
        gap: 1rem;
    }
    .donateRadio, .onlyDonate, .moonDonate {
        @include flex;
    }
}

</style>