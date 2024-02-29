<script setup>
defineProps({
    author: String,
    url_git: String
})
</script>

<template>
    <div>
        <p>
            Desenvolvido por
        </p>
        <a :href="url_git" target="_blank">{{ author }}</a>
    </div>
</template>

<style scoped>
    div{
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 12px;
        border-top: 1px solid #50ff93;
        padding: 20px 0;
        position: fixed;
        bottom: 0;
        left: 0;
        width: 100%;
        margin: 0 auto;
    }

    a{
        color: #c4c4c4;
        margin-left: 5px;
    }

    a:hover{
        color: #50ff93;
        text-decoration: underline;
    }
</style>