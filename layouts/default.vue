<template>
    <v-app>
        <v-app-bar>
            <v-col cols="12" align="end">
                <v-btn @click="logout">logout</v-btn>
            </v-col>
        </v-app-bar>
        <v-navigation-drawer class="mt-5">
            <v-list-item link 
                v-for="(i, index) in buttons"
                :key="index"
                :title="i.title"
                :to="i.to"
                :prepend-icon="i.icon"
            >
    
            </v-list-item>
        </v-navigation-drawer>
        <v-main>
            <!-- <NuxtPage /> -->
            <slot />
        </v-main>
    </v-app>
</template>

<script setup>

const logout = () => {
     navigateTo('/')
}

const buttons = ref([
    {title: 'admin panel', icon: 'mdi-account-alert', to: '/dashboard/admin'},
    {title: 'Database', icon: 'mdi-database', to: '/dashboard/database'},
    {title: 'settings', icon: 'mdi-cog', to: '/dashboard/settings'},
    {title: 'logout', icon: 'mdi-logout', to: '/'},
])

</script>