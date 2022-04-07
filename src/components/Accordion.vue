<template>
    <div class="accordion">
        <p
            class="bold accordion__toggler border-top"
            @click="toggleAccordion()"
            :aria-expanded="isOpen"
        >
            <img v-if="isOpen" src="../assets/icons/minus.png" alt="" />
            <img v-else src="../assets/icons/plus.png" alt="" />
            <slot name="title" />
        </p>
        <div class="accordion__form" v-show="isOpen">
            <slot name="content" />
        </div>
        <div
            class="accordion__form--data font-semiBold"
            v-show="formData && !isOpen"
        >
            <div
                v-for="(dakraam, index) in formData"
                :key="index"
                class="dakraam"
            >
                <div v-if="Object.keys(dakraam).length">
                    <p>Dakraam #{{ ++index }}</p>
                    <p
                        v-for="[key, value] of Object.entries(dakraam)"
                        :key="key"
                    >
                        {{ key }} : {{ value }}
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        formData: {
            type: Array,
            default: null,
        },
    },
    data() {
        return {
            isOpen: false,
        };
    },
    methods: {
        toggleAccordion() {
            this.isOpen = !this.isOpen;
        },
    },
};
</script>

<style scoped>
.accordion__toggler {
    display: flex;
    align-items: center;
    gap: 1rem;
    font-size: 1rem;
    padding: 1.8rem 0;
    margin: 0;
    cursor: pointer;
    font-family: "Gilroy-Bold", sans-serif;
    color: #3a3a3a;
}
.accordion__form,
.accordion__form--data {
    margin-left: 2.2rem;
}
.accordion__form--data p {
    font-size: 14px;
    margin: 2px 0;
    font-family: "Gilroy-SemiBold", sans-serif;
    color: #898989;
}
.accordion__form--data p:first-of-type {
    color: #3a3a3a;
}
.dakraam {
    margin-bottom: 1.2rem;
}

@media only screen and (max-width: 768px) {
    .accordion__form,
    .accordion__form--data {
        margin-left: 0;
    }
}
</style>
