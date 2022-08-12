<template>
    <form @submit.prevent="submit" class="form">
        <!-- <pre>{{form.productName}}</pre>
        <pre>{{form.linkImg}}</pre>
        <pre>{{form.price}}</pre> -->
            <h4 class="title">Наименование товара</h4>
                <input-item 
                    v-model="form.productName.value"
                    id="productName"
                    :class="{input: !form.productName.valid}" 
                    placeholder="Введите наименование товара"
                />
                
            <h4 class="titl">Описание товара</h4>
                <textarea 
                     v-model="card.description"
                    class="textarea" 
                    placeholder="Введите описание товара"
                ></textarea>
            <h4 class="title">Ссылка на изображение товара</h4>
                <input-item
                    v-model="form.linkImg.value"
                    id="linkImg"
                    placeholder="Введите ссылку"
                />
            <h4 class="title">Цена товара</h4>
                <input-item 
                    v-model="form.price.value"
                    id="price" 
                    placeholder="Введите цену"
                />
                
            <button 
                class="btn"
                type="submit" 
                @click="createCard" 
            >
                Добавить товар
            </button>           
    </form> 
</template>

<script>
import InputItem from '@/components/UI/InputItem'
import {useForm} from '../use/form'

const required = val => !!val

export default {
    setup() {
        const form = useForm({
            productName: {
                value: 'Mackbook',
                validators: {required}
            },
            linkImg: {
                value: 'https://s1.1zoom.ru/big3/984/Canada_Parks_Lake_Mountains_Forests_Scenery_Rocky_567540_3840x2400.jpg',
                validators: {required}
            },
            price: {
                value: '10 000руб.',
                validators: {required}
            }
        })
       console.log(form.price);
        function submit() {}

        return {form, submit}
    },
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

    .title::after {
        position: absolute;
        content: url('../../photo1.png');
        top: -7px;
    }

    .titl {
        font-weight: 400;
        font-size: 13px;
        line-height: 13px;
        letter-spacing: -0.02em;
        color: #49485E;
        margin-left: 24px;
        margin-top: 16px;
        margin-bottom: 4px;
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
</style>