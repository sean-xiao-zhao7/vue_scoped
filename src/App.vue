<template>
    <div>
        <the-header></the-header>
        <badge-list></badge-list>
        <user-info
            :full-name="activeUser.name"
            :info-text="activeUser.description"
            :role="activeUser.role"
        ></user-info>
        <course-goals #default="slotProps">
            <h2>{{ slotProps.item }}</h2>
        </course-goals>
    </div>
</template>

<script>
import BadgeListVue from "./components/BadgeList.vue";
import TheHeader from "./components/TheHeader.vue";
import UserInfoVue from "./components/UserInfo.vue";
import CourseGoals from "./components/CouresGoals.vue";

export default {
    components: {
        "the-header": TheHeader,
        "badge-list": BadgeListVue,
        "user-info": UserInfoVue,
        CourseGoals,
    },
    data() {
        return {
            activeUser: {
                name: "Maximilian Schwarzmüller",
                description: "Site owner and admin",
                role: "admin",
            },
        };
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
