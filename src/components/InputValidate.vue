<script setup>
import { reactive, ref, computed } from 'vue'

const input = ref('')

const state = reactive({
    valid: '',
    phone: '',
    location: ''
})

const statusMsg = computed(() => {
    return state.valid ? 'Válido' : 'Inválido'
})

async function httpGetAsync() {

    const response = await fetch(`https://phonevalidation.abstractapi.com/v1?api_key=f6de1e01f261475580610cfec9833cdb&phone=55${input.value}`)
    const { valid, format, location } = await response.json();

    state.valid = valid;
    state.phone = format.local;
    state.location = location;

    //input.value = '';
}

function handleSubmit(e) {
    e.preventDefault();
    httpGetAsync();
}
</script>

<template>
    <form @submit="handleSubmit">
        <input type="text" placeholder="ddd + número" inputmode="numeric" v-model="input"/>
        <button>Validar</button>
    </form>
    <div v-if="state.valid !== ''">
        <h1>
            Informações do telefone
        </h1>

        <p>Status: <span :class="state.valid ? `defaultInfo` : `errorInfo`">{{ statusMsg }}</span></p>
        <div v-if="state.valid == true">
            <p>Telefone: <span class="defaultInfo">{{ state.phone }}</span></p>
            <p>UF: <span class="defaultInfo">{{ state.location }}</span></p>
        </div>
    </div>
</template>

<style scoped>
input {
    width: 200px;
    padding: 10px;
    border-radius: 5px;
    border: none;
    margin: 0 auto;
}

input:focus {
    outline: none;
}

button {
    width: 200px;
    padding: 10px;
    border-radius: 5px;
    border: none;
    margin: 10px auto;
    background-color: #50ff93;
    color: #252525;
    cursor: pointer;
}

form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
}

h1 {
    text-align: center;
    margin: 20px 0 5px 0;
    font-size: 18px;
}

p {
    font-size: 15px;
}

span {
    font-weight: bold;
}

.defaultInfo {
    color: #50ff93;
}

.errorInfo {
    color: #f77474;
}
</style>