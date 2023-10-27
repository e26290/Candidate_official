<template>
    <div class="goForm">
        <div class="container">
            <div class="d-flex justify-content-end">
                <button>留言給我們！</button>
            </div>
        </div>
    </div>

    <div class="donate">
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
</script>

<style scoped lang="scss">
@import "src/css/mixins.scss";

.goForm {
    padding: 8rem 0;

}
.donate {
    // background-image: url();
    background-color: #ccc;
    padding: 8rem 0;
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