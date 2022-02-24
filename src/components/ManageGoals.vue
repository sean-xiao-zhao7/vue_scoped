<template>
    <h2>Manage goals</h2>
    <input type="text" ref="goal" />
    <button @click="setGoal">Set goal</button>
    <teleport to="body">
        <error-alert v-if="dataInvalid">
            <h2>Invalid input</h2>
            <p>Please enter at least 1 character.</p>
            <button @click="closeDialog">Confirm</button>
        </error-alert>
    </teleport>
</template>

<script>
import ErrorAlert from "./ErrorAlert.vue";
export default {
    components: {
        ErrorAlert,
    },
    data() {
        return {
            dataInvalid: false,
        };
    },
    methods: {
        setGoal() {
            const v = this.$refs.goal.value;
            if (v === "") {
                this.dataInvalid = true;
            }
        },
        closeDialog() {
            this.dataInvalid = false;
        },
    },
};
</script>
