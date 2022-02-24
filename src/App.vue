<template>
    <div>
        <the-header></the-header>
        <button @click="setSelectedComp('active-goals')">Active</button>
        <button @click="setSelectedComp('manage-goals')">Manage</button>
        <keep-alive>
            <component :is="currentComp"> </component>
        </keep-alive>
    </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import ActiveGoals from "./components/ActiveGoals.vue";
import ManageGoals from "./components/ManageGoals.vue";

export default {
    components: {
        "the-header": TheHeader,
        ManageGoals,
        ActiveGoals,
    },
    data() {
        return {
            activeUser: {
                name: "Dan",
                description: "Test",
                role: "admin",
            },
            currentComp: "active-component",
        };
    },
    methods: {
        setSelectedComp(newComp) {
            this.currentComp = newComp;
        },
    },
};
</script>

<style>
html {
    font-family: sans-serif;
}

body {
    margin: 0;
}
</style>
