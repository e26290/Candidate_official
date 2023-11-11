<template>
    <footer>
        <ul class="f_nav">
            <li><a href="#">首頁</a></li>
            <li><a href="#contactUs">聯絡我們</a></li>
            <li><a href="#donate">小額捐款</a></li>
        </ul>
        <p class="copyright">© 2023 Gill WUUUU 版權所有，僅做 2023 The F2E 活動專案練習使用。</p>
    </footer>
</template>

<script setup>
</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";
footer {
    background-color: var(--black);
    @include flex;
    flex-direction: column;
    padding: 1.5rem;
    a {
        color: var(--white);

        &:hover {
            color: var(--primary);
        }
    }
    ul {
        display: flex;
        flex-direction: row;
        gap: 2rem;
    }
    .f_nav li:nth-child(-n+2) {
        padding-right: 2rem;
        border-right: solid 1px var(--white);
    }
    .copyright {
        color: var(--white);
    }
}
</style>