<template>
    <div class="container">
        <div class="main">
        <div class="header"><strong>Добавление товара</strong></div>
        <select class="select">
            <option>По умолчанию</option>
            <option>Min</option>
            <option>Max</option>
            <option>По наименованию</option>
        </select>
    </div>
    
    <div class="content">
        <form class="form">
            <h4 class="title">Наименование товара<img class="point" src="../photo1.png"></h4>
                <input 
                    v-bind:value="title"
                    @input="title = $event.target.value" 
                    class="input" 
                    type="text" 
                    placeholder="Введите наименование товара"
                >
            <h4 class="title">Описание товара</h4>
                <textarea class="textarea" placeholder="Введите описание товара"></textarea>
            <h4 class="title">Ссылка на изображение товара<img class="point" src="../photo1.png"></h4>
                <input
                    v-bind:value="img" 
                    @input="img = $event.target.value" 
                    class="input" 
                    type="text" 
                    placeholder="Введите ссылку"
                >
            <h4 class="title">Цена товара<img class="point" src="../photo1.png"></h4>
                <input 
                    v-bind:value="price"
                    @input="price = $event.target.value" 
                    class="input" 
                    type="label" 
                    placeholder="Введите цену"
                >
            
            <button class="btn" type="submit" @click="createCard">Добавить товар</button>           
        </form>
        <div class="grid">
            <div class="card" v-for="card in cards" :key="card">
                <img class="img" :src="card.img">
                <h3 class="titlCard">{{card.title}}</h3>
                <p class="text">{{card.body}}</p>
                <p class="price">{{card.price}}</p>
            </div>
        </div>
    </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            cards: [
                {id: 1, img: require('../photo.svg'), title: 'Наименование товара', body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 2, img: require('../photo.svg'), title: 'Наименование товара', body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 3, img: require('../photo.svg'), title: 'Наименование товара', body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 4, img: require('../photo.svg'), title: 'Наименование товара', body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 5, img: require('../photo.svg'), title: 'Наименование товара', body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 6, img: require('../photo.svg'), title: 'Наименование товара', body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'}
            ],
            title: '',
            img: '',
            price: ''
        }
    },
    methods: {
        createCard() {

        }
    }
}
</script>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    body {
        background: #E5E5E5;
    }

    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

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

    .content {
        display: flex;
        margin-left: 32px;
        margin-right: 32px;
    }

    .form {
        width: 332px;
        height: 440px;
        background: #FFFEFB;
        box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
        border-radius: 4px;
        box-sizing: border-box;
    }

    .title {
        position: relative;
        font-weight: 400;
        font-size: 13px;
        line-height: 13px;
        letter-spacing: -0.02em;
        color: #49485E;
        margin-left: 24px;
        margin-top: 16px;
        margin-bottom: 4px;
    }

    .point {
        width: 4px;
        height: 4px;
        border-radius: 4px;
        position: absolute;
        margin-left: 1px;

    }
    
    .input {
        width: 284px;
        height: 36px;
        background: #FFFEFB;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        border-radius: 4px;
        margin-left: 24px;
        margin-right: 24px;
        border: none;
    }

    .textarea {
        width: 284px;
        height: 108px;
        background: #FFFEFB;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        border-radius: 4px;
        margin-left: 24px;
        margin-right: 24px;
        border: none;
    }

    .btn {
        width: 284px;
        height: 36px;
        background: #EEEEEE;
        border-radius: 10px;
        margin-left: 24px;
        margin-right: 24px;
        margin-top: 24px;
        font-weight: 600;
        font-size: 12px;
        line-height: 15px;
        text-align: center;
        letter-spacing: -0.02em;
        color: #B4B4B4;
        border: none;
    }

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