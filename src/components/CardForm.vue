<template>
    <form @submit.prevent class="form">
            <h4 class="title">Наименование товара<img class="point" src="../../photo1.png"></h4>
                <input-item 
                    v-model="card.title" 
                    placeholder="Введите наименование товара"
                />
                
            <h4 class="title">Описание товара</h4>
                <textarea 
                     v-model="card.description"
                    class="textarea" 
                    placeholder="Введите описание товара"
                ></textarea>
            <h4 class="title">Ссылка на изображение товара<img class="point" src="../../photo1.png"></h4>
                <input-item
                    v-model="card.img"
                    placeholder="Введите ссылку"
                />
            <h4 class="title">Цена товара<img class="point" src="../../photo1.png"></h4>
                <input-item 
                    v-model="card.price" 
                    placeholder="Введите цену"
                />
                
            <button 
                class="btn" 
                @click="createCard" 
            >
                Добавить товар
            </button>           
    </form> 
</template>

<script>
import InputItem from '@/components/UI/InputItem'
export default {
    components: {InputItem},
    data() {
        return {
            card: {
                title: '',
                description: '',
                img: '',
                price: ''
            }
        }
    },
    methods: {
        createCard() {
            this.card.id = Date.now()
            this.$emit('create', this.card)
            this.card = {
                title: '',
                description: '',
                img: '',
                price: ''
            }
        }
    }
}
</script>

<style scoped>
    
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
    
    /* .input {
        width: 284px;
        height: 36px;
        background: #FFFEFB;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        border-radius: 4px;
        margin-left: 24px;
        margin-right: 24px;
        border: none;
    } */

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
</style>