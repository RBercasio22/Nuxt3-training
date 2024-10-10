<template>
    <div class="pa-10">
        <h1>Login Form</h1>
        <v-text-field label="username" v-model="username">

        </v-text-field>
        <v-text-field label="password" v-model="password">

        </v-text-field>
        <v-btn @click="login">
            login
        </v-btn>
    </div>
</template>

<script setup>

const username = ref('')
const password = ref('')

// const routes = useRouter()
// routes.push('/dashboard')

definePageMeta({
    layout: 'main'
})

const login = () => {
    if(username.value === '1' && password.value === '1') {
        navigateTo('/dashboard')
    }
    else {
        alert('Error')
    }
}

</script>