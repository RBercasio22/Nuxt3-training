<template>
    <v-app>
        <v-app-bar>
            <v-col cols="12" align="end">
                <v-btn @click="logout">logout</v-btn>
            </v-col>
        </v-app-bar>
        <v-navigation-drawer>
            <li><NuxtLink to="/dashboard/admin">Click</NuxtLink></li>
            <li><NuxtLink to="/dashboard/settings">settings</NuxtLink></li>
            
            <!-- <v-btn to="dashboard/admin">admin panel</v-btn>
            <v-btn to="/settings">settings</v-btn>
            <v-btn to="/account">account</v-btn> -->
            <div>
            <!-- <v-btn
            v-for="(x, index) in buttons"
            :key="index"
            :title="x.title"
            :to="x.to"
            :icon="x.icon"
            >
             </v-btn> -->
            </div>

          
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
    {title: 'admin panel', icon: 'mdi-lock', to: 'dashboard/admin'},
    {title: 'settings', icon: 'mdi-cog', to: 'dashboard/settings'},
    {title: 'directories', icon: 'mdi-folder-multiple', to: 'dashboard/directories'},
])

</script>