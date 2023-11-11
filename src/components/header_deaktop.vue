<template>
    <header>
        <img src="../assets/img_logo.svg" alt="logo" class="logo">
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
    </header>
</template>

<script setup>
</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";


header {
    background-color: var(--white);
    width: 19rem;
    height: 100vh;
    padding: 1.5rem;
    display: flex;
    align-items: center;
    flex-direction: column;
}
.logo {
    width: 100%;
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
header {
    @include media-breakpoint-up(1024px) {
        display: none;
    }
}

</style>