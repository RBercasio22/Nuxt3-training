<template>
    <v-col cols="12" align="center" class="justify-center">
        <div class="pa-10">
            <h1>Registration Form</h1>

            <v-text-field
                v-for="(x, index) in form"
                :key="index"
                :label="x.label"
                :type="x.type"
                v-model="x.model"
            >
            </v-text-field>
            <v-btn @click="register">
                Register
            </v-btn>

            <div v-for="(i, index) in object" :key="index">
                {{ i.user }}
                <br>
                {{ i.pass }} 
                <br>
                {{ i.rrole }}
            </div>
        </div>
    </v-col>
</template>

<script setup>
definePageMeta({
    layout: 'main'
})

const username = ref('')
const password = ref('')
const role = ref('')
const object = ref([])

const form = ref([
    { label: 'username', model: username, type: 'text' },
    { label: 'password', model: password, type: 'password' },
    { label: 'role', model: role, type: 'text' }
])

const register = () => {
    if (username.value.trim() && password.value.trim() && role.value.trim()) {
        object.value.push({
            user: username.value,
            pass: password.value,
            rrole: role.value
        });
        // Clear the inputs
        username.value = '';
        password.value = '';
        role.value = '';
    } else {
        alert('Error! All fields are required.');
    }
}
</script>
