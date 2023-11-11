<template>
    <div class="radioGrop">
        <label>
            <input type="radio" value="A" v-model="selectedOption"> 單筆捐款
        </label>
        <label>
            <input type="radio" value="B" v-model="selectedOption"> 定期捐款
        </label>
    </div>

    <!-- 單筆選項 -->
    <div v-if="selectedOption === 'A'" class="onlyDonate donateOption">
        <button :class="{ active: selectedOption === 'A' && selectedAmount === 300 }" @click="selectAmount(300)">$ 300</button>
        <button :class="{ active: selectedOption === 'A' && selectedAmount === 600 }" @click="selectAmount(600)">$ 600</button>
        <button :class="{ active: selectedOption === 'A' && selectedAmount === 1200 }" @click="selectAmount(1200)">$ 1,200</button>
        <!-- 自訂金額的欄位 -->
        <input class="customize" type="text" placeholder="輸入自訂金額"
            :class="{ active: selectedOption === 'A' && selectedAmount === 1 }"
            @click="setCustomInputState(true); selectAmount(1)" >
    </div>

    <!-- 定期選項 -->
    <div v-if="selectedOption === 'B'" class="moonDonate donateOption">
        <button :class="{ active: selectedOption === 'B' && selectedAmount === 300 }" @click="selectAmount(300)">$ 300 / 月</button>
        <button :class="{ active: selectedOption === 'B' && selectedAmount === 600 }" @click="selectAmount(600)">$ 600 / 月</button>
        <button :class="{ active: selectedOption === 'B' && selectedAmount === 1200 }" @click="selectAmount(1200)">$ 1,200 / 月</button>
        <!-- 自每月金額的欄位 -->
        <input class="customize" type="text" placeholder="輸入每月自訂金額" 
            :class="{ active: selectedOption === 'B' && selectedAmount === 1 }"
            @click="setCustomInputState(true); selectAmount(1)">
    </div>
</template>

<script setup>
import { ref, watch } from 'vue';

// 預設選擇單筆捐款
const selectedOption = ref('A'); 
// 預設選擇600元
const selectedAmount = ref(600);
const isCustomInputActive = ref(false);
function selectAmount(amount) {
    selectedAmount.value = amount;
    // 當選擇預設金額時，重置自訂輸入框的活躍狀態
    isCustomInputActive.value = false;
}

function setCustomInputState(state) {
    isCustomInputActive.value = state;
}

</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";
.radioGrop {
    @include flex;
}
.donateOption {
    @include flex;
    flex-wrap: wrap;
    button, input {
        background-color: var(--white);
        color: var(--black);
    }
    button {
        white-space: nowrap;
    }
    .active {
        background-color: var(--primary);
        color: var(--white);
    }
    .customize {
        padding: 8px 12px;
        border-radius: 8px;
        border: solid 1px var(--grey_D4);

        &:active, &:focus {
            outline: none;
            color: var(--white);
            
        }
    }
}
</style>