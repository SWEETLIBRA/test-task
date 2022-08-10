<template>
    <div class="grid">
        <card-item 
            v-for="card in cards" 
            :card="card"
            :key="card.id" 
        />    
    </div>
    
</template>

<script>
import CardItem from '@/components/CardItem'
export default {
    components: {CardItem},
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
</style>