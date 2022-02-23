<template>
    <base-card>
        <template v-slot:header>
            <header>
                <div>
                    <h3>{{ fullName }}</h3>
                    <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
                </div>
            </header>
        </template>
        <template v-slot:default>
            <p>{{ infoText }}</p>
        </template>
    </base-card>
</template>

<script>
export default {
    props: ["fullName", "infoText", "role"],
};
</script>
