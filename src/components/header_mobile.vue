<template>
    <header class="header_mobile">
        <div class="container-fluid d-flex justify-content-between">
            <img src="../assets/img_logo_mb.svg" alt="logo" class="logo">
            <div class="nav">
                <a href="#" class="btn-donate">
                    <i class="fa-solid fa-heart"></i>
                    小額捐款
                </a>
                <button type="button" @click="toggleMenu">
                    <i class="fa-solid fa-bars"></i>
                </button>
            </div>
        </div>
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
            <li class="nav_item">
                <a href="#">個人簡介</a>
                <i class="fa-solid fa-arrow-right-long"></i>
            </li>
            <li class="nav_item">
                <a href="#">最新消息</a>
                <i class="fa-solid fa-arrow-right-long"></i>
            </li>
            <li class="nav_item">
                <a href="#">展開行動</a>
                <i class="fa-solid fa-arrow-right-long"></i>
            </li>
            <li class="nav_item">
                <a href="#">政策議題</a>
                <i class="fa-solid fa-arrow-right-long"></i>
            </li>
            <li class="nav_item">
                <a href="#">留言給我們！</a>
                <i class="fa-solid fa-arrow-right-long"></i>
            </li>
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
    display: none;
    width: 100%;
    position: fixed;
    bottom: 0;
    background-color: var(--white);
    padding: 0 0.75rem;
    box-shadow: 0 0 8px 4px rgba(0,0,0,0.15);
    .logo{
        width: 10rem;
    }
    .nav {
        @include flex($a:stretch);
        .btn-donate {
            border-left: solid 1px var(--grey_D4);
            border-right: solid 1px var(--grey_D4);
            padding: 0 2rem;
            @include flex;
        }
        button {
            background-color: transparent;
            color: var(--black);
            padding: 1.5rem;
        }
    }
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
        @include flex($j:space-between);
        a {
            display: block;
            padding: 1.25rem 0;
            border-bottom: dashed 1px var(--grey_CC);
            text-align: left;
            position: relative;
        }
        &:hover {
            color: var(--primary);
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
        a {
            color: var(--grey_9F);
        }
    }
}

@media (max-width: 768px) {
    header {
        display: block;
    }
}
</style>