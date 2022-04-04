<template>
    <div class="flex navigation-buttons">
        <button class="back-btn bold" @click="$parent.$emit('changeComponent', back)">
            <img src="../assets/icons/chevron_pink.png" alt="" />
            Terug
        </button>
        <button
            class="proceed-btn bold"
            @click="$parent.$emit('changeComponent', proceed)"
        >
            Verder
            <img src="../assets/icons/chevron_pink.png" alt="" />
        </button>
    </div>
</template>

<script>
export default {
    props: {
        proceed: {
            type: String,
            required: true,
            default: 'Home'
        },
        back: {
            type: String,
            required: true,
            default: 'Home'
        }
    }
};
</script>

<style></style>
