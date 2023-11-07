<template>
    <header class="header_mobile">
        <!-- TODO 這裡要換logo橫式的 -->
        <img src="../assets/img_logo_m.svg" alt="logo" class="logo">
        <a href="#" class="btn-donate">
            <i class="fa-solid fa-heart"></i>
            小額捐款
        </a>
        <button type="button" @click="toggleMenu">
            <i class="fa-solid fa-bars"></i>
        </button>
    </header>
    <!-- 選單 -->
    <div v-if="showMenu" class="menu_view container-fluid">
        <div class="row fluid">
            <div class="colse_btn" @click="closeMenu">
                關閉
                <i class="fa-solid fa-xmark"></i>
            </div>
        </div>
        <ul class="nav">
            <li class="nav_item"><a href="#">個人簡介</a></li>
            <li class="nav_item"><a href="#">最新消息</a></li>
            <li class="nav_item"><a href="#">展開行動</a></li>
            <li class="nav_item"><a href="#">政策議題</a></li>
            <li class="nav_item"><a href="#">留言給我們！</a></li>
        </ul>

        <a href="#" class="btn-donate">
            <i class="fa-solid fa-heart"></i>
            小額捐款
        </a>
        <ul class="media">
            <li class="m_item"><a href="#"><i class="fa-brands fa-facebook fa-2x"></i></a></li>
            <li class="m_item"><a href="#"><i class="fa-brands fa-square-instagram fa-2x"></i></a></li>
            <li class="m_item"><a href="#"><i class="fa-brands fa-x-twitter fa-2x"></i></a></li>
            <li class="m_item"><a href="#"><i class="fa-brands fa-youtube fa-2x"></i></a></li>
        </ul>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const showMenu = ref(false);

function toggleMenu() {
    showMenu.value = !showMenu.value;
}

function closeMenu() {
    showMenu.value = false;
}
</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";

header {
    width: 100%;
    position: fixed;
    bottom: 0;
    background-color: var(--grey_F3);
}
.menu_view {
    background-color: var(--grey_F3);
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    @include flex($j:flex-start);
    flex-direction: column;
    padding: 1.5rem;
    .fluid {
        width: 100%;
    }
    .colse_btn {
        font-size: 1.25rem;
        text-align: right;
    }
    ul.nav {
        width: 100%;
        height: 100%;
        flex-direction: column;
    }
    .nav_item {
        width: 100%;
        a {
            display: block;
            padding: 1.25rem 0;
            border-bottom: dashed 1px var(--grey_CC);
            text-align: left;
            position: relative;

            // TODO 這邊icon沒有完成
            &::after {
                content: "\uf060";
                display: block;
                width: 1.5rem;
                height: 1.5rem;
                color: var(--primary);
                position: absolute;
                right: 30px;
                top: 50%;
                transform: translateY(-50%);
            }
        }
    }
    .btn-donate {
        width: 100%;
        padding: 12px 0;
        background-color: var(--primary);
        filter: brightness(95%);
        color: var(--white);
        border-radius: 0.5rem;

        &:hover {
            background-color: var(--deepPink);
        }
    }
    .media {
        @include flex($g:1.2rem);
        margin-top: 1.5rem;
    }
}
</style>