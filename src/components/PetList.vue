<template>
    <div>
        <span>{{ title }}</span>
        <ul v-for="(item, index) in value" :key="index">
            <li>{{ item }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    
    name: 'PetList',

    props: {
        title: {
            type: String,
            required: true
        },
        value: Array
    }
}
</script>

<style>
ul {
    list-style-type: none;
}
</style>
