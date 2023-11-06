<template>
    <div>
        <input type="radio" name="radio" value="a" v-model="radioValue" @change="handleChange">
        <label for="radio-a">內容Ａ</label>

        <input type="radio" name="radio" value="b" v-model="radioValue" @change="handleChange">
        <label for="radio-b">內容Ｂ</label>

        <div v-if="radioValue === 'a'">
            內容Ａ
        </div>

        <div v-if="radioValue === 'b'">
            內容Ｂ
        </div>
    </div>
</template>

<script setup>
import { reactive } from 'vue';

const radioValue = reactive('a');

function handleChange() {
    // 更新 v-if 指令的條件
    if (radioValue === 'a') {
        $refs.divA.style.display = 'block';
        $refs.divB.style.display = 'none';
    } else {
        $refs.divA.style.display = 'none';
        $refs.divB.style.display = 'block';
    }
}
</script>

<style scoped lang="scss">

</style>