<template>
    <div class="single-box">
        <h2>{{ title }}</h2>
        <p>{{ message }}</p>
    </div>
</template>

<script>
export default {
    name: 'BoxMessage',

    props: {
        title: {
            type: String,
            default: 'Default Title',
        },
        message: {
            type: String,
            default: 'Default Message',
        },
    },
};
</script>

<style>
.single-box {
    border: 1px solid #333333;
    padding: 10px;
}
</style>
