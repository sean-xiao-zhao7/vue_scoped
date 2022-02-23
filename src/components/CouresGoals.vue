<template>
    <ul v-for="goal in goals" :key="goal">
        <slot :item="goal"></slot>
    </ul>
</template>

<script>
export default {
    data() {
        return {
            goals: ["Finish", "Get girl"],
        };
    },
};
</script>
