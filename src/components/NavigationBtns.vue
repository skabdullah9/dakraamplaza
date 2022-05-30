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
            class="proceed-btn"
            :class="{'active': btnActive}"
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
            default: "Home",
        },
        back: {
            type: String,
            required: true,
            default: "Home",
        },
        btnActive: {
            type: Boolean,
            required: true,
            default: false,
        },
    },
};
</script>

<style>
.navigation-buttons {
    padding-bottom: 3rem ;
    padding-top: 1rem;
    justify-content: space-between;
}
.navigation-buttons button {
    color: #ff0083;

    padding: 1rem 3.5rem;
    font-size: 1rem;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1rem;
    font-family: "Gilroy-SemiBold", sans-serif;
}
.proceed-btn {
    pointer-events: none;
    border: 1px solid #ff0083;
}
.proceed-btn.active {
    background-color: #ff0083;
    color: white;
    pointer-events: all;
}
.proceed-btn.active img {
    filter: brightness(0) invert(1);
}
.back-btn {
    padding-left: 0 !important;
}
.send-request {
    padding-left: 22px !important;
    padding-right: 22px !important;
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
