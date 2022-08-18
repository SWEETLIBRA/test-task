<template>
    <div class="container">
        <Main />
        
        <div class="content">
            <CardForm 
                @create="createCard" 
            />
            <CardList 
                :cards="cards"
            />
        </div>
    </div>
</template>

<script>
import Main from '@/components/Main'
import CardForm from '@/components/CardForm'
import CardList from '@/components/CardList'

export default {
    components: {Main, CardForm, CardList
    },
    data() {
        return {
            cards: [
                {id: 1, img: require('../photo.svg'), title: 'Наименование товара', description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 2, img: require('../photo.svg'), title: 'Наименование товара', description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 3, img: require('../photo.svg'), title: 'Наименование товара', description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 4, img: require('../photo.svg'), title: 'Наименование товара', description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 5, img: require('../photo.svg'), title: 'Наименование товара', description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'},
                {id: 6, img: require('../photo.svg'), title: 'Наименование товара', description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 руб.'}
            ],
        }
    },
    methods: {
        createCard(card) {
            this.cards.push(card);
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

    .content {
        display: flex;
        margin-left: 32px;
        margin-right: 32px;
    }
</style>