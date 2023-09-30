<template>
    <a href="#">
        <div class="action-button">
            {{ text }}
        </div>
    </a>
</template>
<script>
export default {
    props: {
        text: {
            type: String,
            default: 'Subscribe to monthly newsletter'
        }
    }
}
</script>