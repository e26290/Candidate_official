<template>
    <div id="banner">
        <div class="pic"></div>
        <div class="text-title">
            <h1 class="bigTitle">貓若回頭</h1>
            <h1 class="bigTitle">不是貓沙，就是<span class="yellow">罐頭</span></h1>
            <span class="slogan">我不是渣，只是心懷天下，想給每個貓咪一個家。</span>
            <div class="pinkbox">
                <span class="boxTitle">懇請支持</span>
                <i class="fa-regular fa-hand-back-fist fa-2x"></i>
            </div>
        </div>
        <div class="text-name">
            <span class="enName">CHI & YUNA</span>
            <h2 class="twName">吉吉語娜</h2>
        </div>
        <!-- TODO 連結待補 -->
        <div class="alert_donate">
            <div class="info">
                您的一點小小捐款，可以為流浪動物帶來巨大的改變。牠們將不再挨餓、受凍、受傷，而是可以健康快樂地生活。
            </div>
            <div class="a_links">
                <a href="#">單筆捐款</a>
                <a href="#">定期捐款</a>
            </div>
        </div>
    </div>
</template>

<script setup>
</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";
#banner {
    width: 100%;
    height: 100vh;
    position: relative;
    .pic {
        width: 100%;
        height: 100%;
        background-image: url(/images/img_banner.png);
        background-position: center 30%;
        background-size: cover;
        background-repeat: no-repeat;
    }
    .text-title {
        position: absolute;
        left: 6rem;
        bottom: 8rem;
        text-align: left;
        .bigTitle {
            font-size: 4rem;
            font-weight: bold;
            font-weight: 900;
        }
        .yellow {
            margin-left: 0.2rem;
            padding: 0.25rem 0.8rem;
            border-radius: 0.5rem;
            background-color: var(--yellow);
        }
        .slogan {
            display: inline-block;
            margin-top: 0.25rem;
            font-size: 1.25rem;
            letter-spacing: 0.5rem;
        }
        .pinkbox {
            background-color: rgba(#000, 0.3);
            color: var(--white);
            margin-top: 0.5rem;
            padding: 0.7rem 0.5rem;
            border-radius: 0.5rem;
            @include flex;
            width: 40%;
            .boxTitle {
                font-size: 1.5rem;
                font-weight: 700;
                letter-spacing: 0.2rem;
                display: inline-block;
            }
        }
    }
    .text-name {
        position: absolute;
        top: 4rem;
        right: 6rem;
        .enName {
            font-size: 1.7rem;
            font-weight: 900;
        }
        .twName {
            font-size: 2.5rem;
            font-weight: 900;
        }
        .enName, .twName {
            color: var(--white);
        }
    }
    .alert_donate {
        position: absolute;
        right: 2rem;
        bottom: 2rem;
        background-color: var(--white);
        max-width: 500px;
        border-radius: 0.5rem;
        @include flex($a:stretch, $g: 0rem);
        .info {
            padding: 1rem;
            border-right: solid 1px var(--grey_D4);
            @include flex;
            text-align: left;
        }
        .a_links {
            @include flex($g: 0rem);
            flex-direction: column;
            a{
                white-space: nowrap;
                padding: 1rem;
            }
            a:nth-child(1) {
                border-bottom: solid 1px var(--grey_D4);
            }
        }
    }
}

@media (max-width: 1200px) {
    #banner .text-title {
        left: 2rem;
        bottom: 2rem;
        .bigTitle {
            font-size: 3rem;
        }
    }
    #banner .text-name {
        top: 2rem;
        right: 2rem;
    }
}
</style>