<template>
    <form @submit.prevent="submitForm" class="contactUs_form">
        <div class="mb-3 form_item">
            <label for="name" class="form-label">名字</label>
            <input v-model="name" type="text" class="form-control" id="name" placeholder="您的大名" required>
        </div>
        <div class="mb-3 form_item">
            <label for="email" class="form-label">信箱</label>
            <input v-model="email" type="email" class="form-control" id="email" placeholder="exsample@example.com" required>
        </div>
        <div class="mb-3 form_item">
            <label for="phone" class="form-label">電話</label>
            <input v-model="phone" type="tel" class="form-control" id="phone" placeholder="09-" required>
        </div>
        <div class="mb-3 form_item">
            <label for="message" class="form-label">留言</label>
            <textarea v-model="message" class="form-control" id="message" rows="3" required></textarea>
        </div>
        <div class="mb-3 form_check">
            <input v-model="agreeTerms" type="checkbox" class="form-check-input" id="agreeTerms" required>
            <label class="form-check-label" for="agreeTerms">我同意任何無理的要求 喵 ฅ^•ﻌ•^ฅ</label>
        </div>

        <button type="submit" class="btn btn-primary form_btn">送出表單</button>
    </form>

    <div class="alert alert-success mt-3" v-if="formSubmitted">
        表單已成功送出！
    </div>
</template>

<script setup>
import { ref } from 'vue';

const name = ref('');
const phone = ref('');
const message = ref('');
const agreeTerms = ref(false);
const formSubmitted = ref(false);

function submitForm() {
    // 電話號碼格式驗證，必須以 "09" 開頭
    const phoneRegex = /^09\d{8}$/;

    if (!phoneRegex.test(phone.value)) {
        alert('請輸入正確的電話號碼（09 開頭的 10 位數字）！');
    } else if (!name.value || !message.value || !agreeTerms.value) {
        alert('您尚未填寫完畢');
    } else {
        // 這裡可以處理表單送出的邏輯，例如發送 API 請求等等
        // 在這個範例中，我們只是將表單設置為已提交
        formSubmitted.value = true;
        // 設定延遲關閉視窗，延遲時間為 2000 毫秒 (2 秒)
        setTimeout(() => {
            formSubmitted.value = false;
        }, 2000);
    }
}
</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";
.contactUs_form {
    padding: 0 3rem;
    .form_item {
        @include flex($a:start, $g:0rem);
        flex-direction: column;
    }
    .form_check {
        @include flex($a:stretch, $g:0.5rem);
    }
    .alert {
        position: absolute;
        top: 0;
    }
    .form_btn {
        margin-top: 1rem;
    }

    @include media-breakpoint-up(425px) {
        padding: 0;
    }
}
</style>