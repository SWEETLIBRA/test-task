<template>
    <input 
        
        :value="modelValue"
        @input="updateInput"
        :placeholder="placeholder"
        :class="{error: error}"
        class="input" 
        type="text"
    >
</template>

<script>
export default {
    name: 'my-input',
    props: {
        modelValue: [String, Number],
        placeholder: [String],
        error: Boolean
    },
    methods: {
        updateInput(e) {
            this.$emit('update:modelValue', e.target.value);
        }
    }
}
</script>

<style scoped>
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

    .error {
        border: 1px solid #FF8484;
    }
</style>