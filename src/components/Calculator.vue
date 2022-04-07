<template>
    <div class="calculator">
        <transition name="fade" mode="out-in">
            <keep-alive>
                <component
                    :is="activeComponent"
                    @changeComponent="changeComponent"
                />
            </keep-alive>
        </transition>
    </div>
</template>

<script>
import Home from "./Home.vue";
import Step1 from "./Step1.vue";
import Step2 from "./Step2.vue";
import Step3 from "./Step3.vue";
import Step4 from "./Step4.vue";
import ThankYou from "./ThankYou.vue";

export default {
    name: "Calculator",
    components: {
        Home,
        Step1,
        Step2,
        Step3,
        Step4,
        ThankYou,
    },
    data() {
        return {
            activeComponent: "Home",
        };
    },
    methods: {
        changeComponent(comp) {
            this.activeComponent = comp;
        },
    },
};
</script>

<style>
/* .calculator {
    padding: 3rem 1rem;
} */
.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.2s ease-out;
}
.step-1,
.step-2,
.step-3,
.step-4 {
    padding: 1rem;
}
.steps__title {
    font-size: calc(26px + (40 - 26) * ((100vw - 300px) / (1600 - 300)));
    max-width: 23ch;
    text-align: center;
    margin: 3rem auto;
    color: #3a3a3a;
    line-height: 48px;
    font-family: "Gilroy-Bold", sans-serif;
}
.steps__no {
    color: #898989;
    font-size: 18px;
    font-weight: 100;
    margin-bottom: 0;
    font-family: "Gilroy-Regular", sans-serif;
}
.steps__question {
    margin-top: 0;
    margin-bottom: 10px;
    color: #3a3a3a;
    font-family: "Gilroy-Bold", sans-serif;
}
.steps__help {
    color: #898989;
    white-space: nowrap;
    font-size: 1rem;
    font-family: "Gilroy-Regular", sans-serif;
    margin-top: 0;
    margin-bottom: 1.25rem;
}
input[type="text"],
input[type="number"],
input[type="tel"],
input[type="email"],
textarea {
    padding: 1.25rem 2.5rem;
    font-size: 1rem;
    border: 1px solid #c4c4c4;
    appearance: none;
    cursor: pointer;
    outline: none;
    font-family: "Gilroy-Medium", sans-serif;
    width: 100%;
    margin: 0;
    margin-bottom: 1rem;
}
textarea {
    resize: vertical;
    margin-bottom: 0;
}
input[type="text"]:focus,
input[type="number"]:focus,
input[type="tel"]:focus,
input[type="email"]:focus,
textarea:focus,
div[data-type="select"] select:focus {
    border-color: #ff0083;
}

/* CUSTOM DROPDOWN MENU (SELECT) */
div[data-type="select"] {
    position: relative;
    margin-bottom: 1rem;
}
div[data-type="select"]::after {
    content: url("../assets/icons/chevron_dark.png");
    position: absolute;
    top: 50%;
    right: 3rem;
    transform: translateY(-50%);
    cursor: pointer;
    pointer-events: revert;
    z-index: -1;
}
div[data-type="select"] select {
    padding: 1.25rem 2.5rem;
    font-size: 1rem;
    border: 1px solid #c4c4c4;
    width: 100%;
    max-width: 366px;
    height: 68px;
    margin: 0;
    appearance: none;
    cursor: pointer;
    outline: none;
    font-family: "Gilroy-Medium", sans-serif;
    background-color: transparent;
}
div[data-type="select"] select option {
    color: #3a3a3a;
    padding: 1rem 0 !important;
}
div[data-type="select"] select[data-placeholder-selected] {
    color: #999999;
}

/* ADD & REMOVE FORM ELEMENTS - BUTTONS STYLING */
.formulate-input-group-add-more {
    text-align: right;
}
.formulate-input-group-add-more button {
    color: #ff0083;
    padding-right: 0;
    font-family: "Gilroy-SemiBold", sans-serif;
    font-size: 1rem;
    margin-top: 0.5rem;
    margin-bottom: 1.8rem;
}
.formulate-input-group-repeatable-remove {
    cursor: pointer;
    display: block;
    text-align: right;
    visibility: hidden;
    padding: 1.25rem 0;
    font-size: 1rem;
    font-family: "Gilroy-SemiBold", sans-serif;
    line-height: 19px;
}
.formulate-input-group-repeatable-remove::after {
    content: url(../assets/icons/trash.png) " Verwijder";
    visibility: visible;
    color: #898989;
    font-size: 1rem;
}
.formulate-input-group-repeatable:first-of-type
    .formulate-input-group-repeatable-remove {
    display: none;
}

/* CUSTOM CHECKBOX (RADIO) */
.checkbox-container {
    display: flex;
    align-items: center;
    margin-top: 0.6rem;
    margin-bottom: 3rem;
}
.checkbox-container div:last-of-type {
    margin: 0 auto;
}
.checkbox-container .formulate-input-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
}
.checkbox-container .formulate-input-wrapper > label {
    line-height: 24px;
    margin-left: 0.9rem;
    display: block;
    font-size: 1rem;
    height: 100%;
}
.checkbox-container .formulate-input-element-decorator {
    width: 21px;
    height: 21px;
    background-color: #f0f0f0;
    display: flex;
    justify-content: center;
    align-items: center;
}
.checkbox-container input[type="radio"],
.checkbox-container input[type="checkbox"] {
    display: none;
}
.checkbox-container input[type="radio"] + label::after,
.checkbox-container input[type="checkbox"] + label::after {
    content: url(../assets/icons/correct.png);
    display: none;
}
.checkbox-container input[type="radio"]:checked + label::after,
.checkbox-container input[type="checkbox"]:checked + label::after {
    display: block;
}
.checkbox-label {
    font-family: "Gilroy-Bold", sans-serif;
    font-size: 1rem;
    white-space: nowrap;
    color: #3a3a3a;
    padding-top: 3.1rem;
    display: block;
}

[data-type="checkbox"] .checkbox-container {
    flex-direction: column;
    align-items: start;
}
[data-type="checkbox"] .checkbox-container div:last-of-type {
    margin: 0;
}
.formulate-input-element--checkbox {
    display: flex;
    gap: 1rem;
    align-items: start;
}

.formulate-input-errors {
    margin-top: 0;
    color: #ff0083;
    opacity: 0.6;
}

@media only screen and (max-width: 768px) {
    .steps__title {
        line-height: calc(29px + (48 - 29) * ((100vw - 300px) / (1600 - 300)));
        margin: 0 auto;
    }
    .steps__help,
    .show-more-help {
        white-space: normal;
    }
    .checkbox-label {
        white-space: normal;
    }
    div[data-type="select"]::after {
        right: 2rem;
    }
    input[type="text"],
    input[type="number"],
    input[type="tel"],
    input[type="email"],
    textarea,
    div[data-type="select"] select {
        padding: 1.25rem;
    }
}
</style>
