<template>
    <div>
        <span>{{ title }}</span>
        <ul v-for="(item, index) in value" :key="index">
            <li>{{ item }}</li>
        </ul>
    </div>
</template>

<script>
import { constants } from 'crypto';
export default {
    
    name: 'PetList',

    props: {
        title: {
            type: String,
            required: true
        },
        value: Array
    },

    mounted () {
        console.log(this.value)
    }
}
</script>

<style>
ul {
    list-style-type: none;
}
</style>
