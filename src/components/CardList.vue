<template>
    <div class="grid">
        <div class="card" v-for="card in cards" :key="card">
            <img class="img" :src="card.img">
            <h3 class="titlCard">{{card.title}}</h3>
            <p class="text">{{card.body}}</p>
            <p class="price">{{card.price}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        cards: {
            type: Array,
            required: true
        }
    }
}
</script>

<style scoped>
    .grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 16px;
        margin-left: 16px;
        cursor: pointer;      
    }

    .card {
        width: 332px;
        height: 423px;
        background: #FFFEFB;
        box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
        border-radius: 4px;
        box-sizing: border-box;
    }

    .img {
        width: 332px;
        height: 200px;
        border-radius: 4px 4px 0px 0px;
    }

    .titlCard {
        font-weight: 600;
        font-size: 20px;
        line-height: 25px;
        color: #3F3F3F;
        margin: 15px;
    }

    .text {
        font-weight: 400;
        font-size: 16px;
        line-height: 20px;
        color: #3F3F3F;
        margin: 16px;
    }

    .price {
        font-weight: 600;
        font-size: 24px;
        line-height: 30px;
        color: #3F3F3F;
        margin-top: 32px;
        margin-left: 16px;
    }
</style>