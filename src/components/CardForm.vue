<template>
    <form @submit.prevent="submit" class="form">
            <h4 class="title">Наименование товара</h4>
                <input-item 
                    v-model="form.productName.value"
                    @blur="form.productName.blur"
                    id="productName"
                    :class="{error: !form.productName.valid && form.productName.touched}" 
                    placeholder="Введите наименование товара"
                />
                <small 
                    style="color: #FF8484; padding-left: 24px;font-weight: 400;font-size: 8px;line-height: 10px;letter-spacing: -0.02em;"
                    v-if="form.productName.touched && form.productName.errors.required">
                    Поле является обязательным</small>
                
            <h4 class="titl">Описание товара</h4>
                <textarea 
                     v-model="card.description"
                    class="textarea" 
                    placeholder="Введите описание товара"
                ></textarea>
            <h4 class="title">Ссылка на изображение товара</h4>
                <input-item
                    v-model="form.linkImg.value"
                    @blur="form.linkImg.blur"
                    id="linkImg"
                    :class="{error: !form.linkImg.valid && form.linkImg.touched}"
                    placeholder="Введите ссылку"
                />
                <small 
                    style="color: #FF8484; padding-left: 24px;font-weight: 400;font-size: 8px;line-height: 10px;letter-spacing: -0.02em;"
                    v-if="form.linkImg.touched && form.linkImg.errors.required">
                    Поле является обязательным</small>
            <h4 class="title">Цена товара</h4>
                <input-item 
                    v-model="form.price.value"
                    @blur="form.price.blur"
                    id="price"
                    :class="{error: !form.price.valid && form.price.touched}" 
                    placeholder="Введите цену"
                />
                <small 
                    style="color: #FF8484; padding-left: 24px;font-weight: 400;font-size: 8px;line-height: 10px;letter-spacing: -0.02em;"
                    v-if="form.price.touched && form.price.errors.required">
                    Поле является обязательным</small>
            <button 
                class="btn"
                type="submit" 
                @click="createCard"
                :disabled="!form.valid" 
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
                value: '',
                validators: {required}
            },
            linkImg: {
                value: '',
                validators: {required}
            },
            price: {
                value: '',
                validators: {required}
            }
        })

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
        background: #7BAE73;
        border-radius: 10px;
        margin-left: 24px;
        margin-right: 24px;
        margin-top: 24px;
        font-weight: 600;
        font-size: 12px;
        line-height: 15px;
        text-align: center;
        letter-spacing: -0.02em;
        color: #FFFFFF;
        border: none;
    }

    .btn:hover {
    cursor: pointer;
    opacity: 0.8;
}

.btn:disabled {
    cursor: not-allowed;
    opacity: 1;
    background: #eee;
    border-color: #ddd;
    color: #999;
}
</style>