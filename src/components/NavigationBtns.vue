<template>
    <div class="flex navigation-buttons" id="navigation-buttons">
        <button
            class="back-btn"
            @click="$parent.$emit('changeComponent', back)"
        >
            <img src="../assets/icons/chevron_pink.png" alt="" />
            Terug
        </button>
        <button
            class="proceed-btn active"
            @click="$parent.$emit('changeComponent', proceed)"
        >
            {{ proceedBtnValue }}
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
            default: "Home",
        },
        back: {
            type: String,
            required: true,
            default: "Home",
        },
        proceedBtnValue: {
            type: String,
            default: "Verder",
        },
    },
};
</script>

<style>
.navigation-buttons {
    padding: 3rem 0;
    justify-content: space-between;
}
.navigation-buttons button {
    color: #ff0083;
    border: 1px solid #ff0083;
    padding: 1rem 3.5rem;
    font-size: 1rem;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1rem;
    font-family: "Gilroy-SemiBold", sans-serif;
}
.proceed-btn.active {
    background-color: #ff0083;
    color: white;
}
.proceed-btn.active img {
    filter: brightness(0) invert(1);
}
@media only screen and (max-width: 768px) {
    #navigation-buttons {
        flex-direction: column-reverse;
        padding: 1.8rem 0;
    }
    #navigation-buttons .back-btn {
        border: none;
    }
}
</style>
