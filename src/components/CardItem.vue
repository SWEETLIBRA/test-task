<template>
    <div class="card" >
        <img class="img" :src="card.img">
        <h3 class="titleCard">{{card.title}}</h3>
        <p class="text">{{card.description}}</p>
        <p class="price">{{card.price}}</p>
    </div>
</template>

<script>
export default {
    name: 'card-item',
    props: {
        card: {
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped>
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

    .titleCard {
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