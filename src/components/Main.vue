<template>
    <div class="main">
            <div class="header"><strong>Добавление товара</strong></div>
                <select class="select">
                    <option>По умолчанию</option>
                    <option>Min</option>
                    <option>Max</option>
                    <option>По наименованию</option>
                </select>
        </div>
</template>

<script>
export default {
    data() {
        return {
            
        }
    }
}
</script>

<style scoped>
     .main {
        display: flex;
        padding: 32px 32px 16px 32px;
    }

    .header {
        margin-right: 1005px;
        width: 247px;
        height: 35px;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        color: #3F3F3F;
    }

    .select {
        background: #FFFEFB;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        border-radius: 4px;
        font-weight: 400;
        font-size: 12px;
        line-height: 15px;
        color: #B4B4B4;
        width: 121.49px;
        height: 36px;
        border: none;
    }
</style>