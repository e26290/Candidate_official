<template>
    <div class="about tbp">
        <div class="about_img"></div>
        <div class="basic_info">
            <span class="sectitle">身段最軟 Ｑ 的立委候選人</span>
            <h2 class="name">吉吉語娜<span class="enName">CHICHI & YUNA</span></h2>
        </div>
    
        <div class="about_info">
            <div class="about_box">
                <span class="slogan">1 + 1 就是大於 2</span>
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
        <div class="person_img">
            <img src="/images/img_person_1.png" alt="語娜裝可愛">
        </div>
    </div>

    <timeline />

    <div class="activity tbp">
        <div class="container">
            <div class="sectionTitle">展開行動</div>

            <Carousel_vue />

            <h4 class="activity_secTitle">
                <i class="fa-solid fa-star" style="color: #ffc32a;"></i>
                目前我們已經達成 ...
            </h4>
            <div class="row goal">
                <div class="col-md-3 card_goal" v-for="data in goal">
                    <span class="number">{{ data.number }}</span>
                    <hr class="hr">
                    <span class="name">{{ data.name }}</span>
                </div>
            </div>
            
        </div>
        <div class="person_img">
            <img src="/images/img_person_2.png" alt="語娜驚訝">
        </div>
    </div>

    <div class="policy tbp">
        <div class="container">
            <div class="sectionTitle">政策議題</div>
            <div class="row">
                <div class="col-md-4" v-for="data in policies">
                    <div class="card_policy">
                        <span class="bigNmuber">{{ data.number }}</span>
                        <h3 class="name">{{ data.name }}</h3>
                        <div class="pinkBox"></div>
                        <ol>
                            <li v-for="item in (data.items)">{{ item }}</li>
                        </ol>
                    </div>
                </div>
            </div>
        </div>
        <div class="person_img">
            <!-- 這張拿去ai重算 -->
            <img src="/images/img_person_3.png" alt="吉吉比讚">
        </div>
    </div>

    <!-- TODO p高度調整 -->
    <div class="contactUs">
        <div class="container">
            <div class="row d-flex justify-content-end">
                <div class="col-md-6">
                    <h3>感謝您瀏覽我們的網頁</h3>
                    <p>如果您對政策服務項目感興趣或者對我們有任何的建議，歡迎留言給我們，我們將在收到資料後儘快與您聯絡。再次感謝您的光臨!</p>
                    <!-- TODO 把表單切出去 -->
                    <form class="contactUs_form">
                        <div class="mb-3 form_item">
                            <label for="exampleFormControlInput1" class="form-label">姓名</label>
                            <input type="name" class="form-control" id="exampleFormControlInput1" placeholder="您的大名">
                        </div>
                        <div class="mb-3 form_item">
                            <label for="exampleFormControlInput1" class="form-label">信箱</label>
                            <input type="email" class="form-control" id="exampleFormControlInput1" placeholder="name@example.com">
                        </div>
                        <div class="mb-3 form_item">
                            <label for="exampleFormControlInput1" class="form-label">手機</label>
                            <input type="tel" class="form-control" id="exampleFormControlInput1" placeholder="09-">
                        </div>
                        <div class="mb-3 form_item">
                            <label for="exampleFormControlTextarea1" class="form-label">留言</label>
                            <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
                        </div>
                        <div class="mb-3 form-check">
                            <input type="checkbox" class="form-check-input" id="exampleCheck1">
                            <label class="form-check-label" for="exampleCheck1">我同意您的任何無理的要求 喵 ฅ^•ﻌ•^ฅ</label>
                        </div>
                        <button type="submit" class="btn btn-primary">送出留言</button>
                    </form>
                    <!-- 表單欄位：
                        1. 您的姓名
                        2. 您的 Email
                        3. 您的手機
                        4. 您的建言
                        5. 送出意見按鈕 -->
                </div>
            </div>
        </div>
    </div>

    <div class="donate tbp">
        <div class="mask"></div>
        <div class="container">
            <div class="row d-flex justify-content-end">
                <div class="col-md-6 content">
                    <h3>因為您 讓弱勢貓咪得到幫助</h3>
                    <donate_form />
                    <!-- 下面要刪除 -->
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
import Carousel_vue from './carousel.vue';
import donate_form from './donate_form.vue';
import { reactive } from 'vue';

const goal = reactive([
    {
        number: '45',
        name: '活動場次'
    },{
        number: '100 h',
        name: '活動時數'
    },{
        number: '300 k',
        name: '參與人次'
    }
]);

const policies = reactive([
    {
        number: '01',
        name: `推動寵物醫療
            保障方案`,
        items: [
            '設立寵物醫療基金：每年撥款新台幣 10 億元，專款專用於支援家庭寵物的醫療費用。',
            '提供醫療補助：每隻寵物每年可獲得高達新台幣 20,000 元的醫療補助，減輕飼主的經濟壓力。',
            '合作動物醫院：目前已有和超過 200 家動物醫院進行初步的合作討論。'
        ]
    },{
        number: '02',
        name: `推廣寵物休閒與
            娛樂場所`,
        items: [
            '建立寵物公園：每年撥款新台幣 5 億元，用於在各大都市建立專屬的寵物公園。根據初步規劃，預計在第一年內，將在全國範圍內建立至少 10 座寵物公園。',
            '推廣寵物友善商家：鼓勵商家提供寵物友善的環境，並為參與的商家提供稅收優惠。預計在政策實施後的首年，將有超過 500 家商家加入此計畫。',
            '舉辦寵物活動和工作坊：與各大寵物社團和組織合作，每年舉辦至少 5 場大型的寵物活動，包括寵物才藝比賽、飼養知識工作坊等。'
        ]
    },{
        number: '03',
        name: `推廣寵物飼養教育
            更加專業`,
        items: [
            '建立寵物飼養教育中心：每年撥款新台幣 3 億元，用於在全國各地建立專業的寵物飼養教育中心。預計在第一年內，在全國至少 5 大城市設立教育中心。',
            '推廣寵物飼養課程：與學校、社區組織和寵物社團合作，推出一系列免費的寵物飼養課程。預計每年將有超過 10,000 名市民受益。',
            '製作教育資料：出版寵物飼養手冊、影片和線上課程，讓所有有意飼養寵物的家庭都能輕鬆取得正確的知識。'
        ]
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
.person_img  {
        position: absolute;
        left: 0;
        bottom: 0;
        img {
            transform: scale(0.5);
            transform-origin: left bottom;
        }
    }
// ------------------------------------------------------------------------

.about {
    position: relative;
    background-color: var(--grey_F3);
    padding: 3rem 0;
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
        max-width: 55%;
        padding: 2.5rem;
        padding-bottom: 3.5rem;
        @include flex($a:end);
        flex-direction: column;
        position: relative;
        span, h2 {
            width: 60%;
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
        top: -2rem;
        .about_box {
            background-color: var(--white);
            max-width: 80%;
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
    background-color: var(--grey_F3);
    position: relative;
    .activity_secTitle {
        display: block;
        margin-top: 3rem;
        margin-bottom: 2rem;
    }
    .goal {
        justify-content: center;
    }
    .card_goal {
        @include flex($g:0.2rem);
        flex-direction: column;
        .hr {
            background: var(--primary);
            height: 2px;
            width: 40px;
            opacity: 1;
            border: none;
        }
    }
    .number {
        font-size: 3.5rem;
        font-weight: 700;
        line-height: 100%;
        color: var(--deepPink);
    }
}
.policy {
    position: relative;
    .card_policy {
        background-color: var(--lightYellow);
        border-radius: 0.5rem;
        position: relative;
        padding: 1.5rem;
        margin-top: 1rem;
        @include flex($g:0.2rem);
        flex-direction: column;
        .pinkBox {
            width: 0.25rem;
            height: 0.25rem;
            background-color: var(--primary);
            position: relative;
            
            &::before, &::after {
                content: "";
                width: 0.25rem;
                height: 0.25rem;
                position: absolute;
                background-color: var(--primary);
            }
            &::before {
                left: -1rem;
            }
            &::after {
                left: 1rem;
            }
        }
        .name {
            white-space: pre-line;
        }
        ol {
            margin-top: 1rem;
        }
        li {
            text-align: left;
            margin-bottom: 1rem;
        }
    }
    .bigNmuber {
        font-size: 3rem;
        font-weight: 500;
        line-height: 100%;
        color: var(--grey_66);
        position: relative;
        top: -3rem;
    }
}
.contactUs {
    background-image: url(/images/img_conact_bg.png);
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    padding: 16rem 0;
    h3 {
        font-size: 1.5rem;
    }
    p {
        color: var(--grey_33);
    }
    .contactUs_form {
        .form_item {
            @include flex($a:start, $g:0.2rem);
            flex-direction: column;
        }
    }
}
.donate {
    border-top: solid 1px var(--white);
    background-image: url(/images/img_donate_bg.png);
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    .content {
        @include flex;
        flex-direction: column;
    }
    .donateRadio, .onlyDonate, .moonDonate {
        @include flex;
    }
}

</style>