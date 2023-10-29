<template>
    <div class="about tbp">
        <div class="basic_info">
            <span>最軟Ｑ的候選人</span>
            <!-- Name -->
            <h2>ＱＱＱ</h2>
        </div>
    
        <div class="about_info">
            <div class="about_box">
                <span class="slogan">slogan</span>
                <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>
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
    .basic_info {
        background-color: var(--primary-color);
        max-width: 60%;
        padding: 2.5rem;
        @include flex($a:end);
        flex-direction: column;
        span, h2 {
            width: 45%;
            text-align: left;
        }
    }
    .about_info {
        @include flex($j:end);
        position: relative;
        top: -30px;
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