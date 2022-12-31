<template>
    <v-app id="inspire">

        <v-app-bar flat>
            <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

            <v-toolbar-title>Application</v-toolbar-title>
        </v-app-bar>

        <v-navigation-drawer v-model="drawer">
            <!--  -->
        </v-navigation-drawer>

        <v-main>
            <NuxtPage></NuxtPage>
        </v-main>
    </v-app>
</template>
  
<script>
export default {
    name: "DefaultLayout",
    data () {
        return {
            drawer: true,
            items: [
                {
                    icon: "mdi-chart-donut-variant",
                    title: "Realtime",
                    to: "/",
                },
                {
                    icon: "mdi-history",
                    title: "Offline",
                    to: "/offline",
                },
            ],
            title: "SATDEX",
        };
    },
};
</script>
<style>
html {
    overflow-y: auto;
}

.theme--light.v-navigation-drawer:not(.v-navigation-drawer--floating) .v-navigation-drawer__border {
    background-color: transparent;
}
</style>

<style scoped>
.icon {
    border-radius: 50%;
    box-shadow: 0px 0px 0px 6px #752bdf;
    width: 20px;
    height: 20px;
    margin-left: 35px;
    margin-right: 15px;
}

.v-list-item {
    align-items: center;
    display: flex;
    flex: 1 1 100%;
    letter-spacing: normal;
    min-height: 48px;
    outline: none;
    padding: 0 16px;
    position: relative;
    text-decoration: none;
    border-radius: 8px;
    margin: 10px 15px;
    font-weight: 500;
}
</style>