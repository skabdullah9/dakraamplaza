<template>
    <div>
        <transition name="fade" mode="out-in">
            <component
                :is="activeComponent"
                @changeComponent="changeComponent"
            />
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
        ThankYou
    },
    data() {
        return {
            activeComponent: "Home",
            stepsProgress: 1,
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
.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.4s ease-out;
}
.steps__title {
    font-size: 40px;
    max-width: 23ch;
    text-align: center;
    margin: 3rem auto;
    color: #3A3A3A;
    line-height: 48px;
    font-family: 'Gilroy-Bold', sans-serif;
}
.steps__no {
    color: #898989;
    font-size: 18px;
    font-weight: 100;
    margin-bottom: 0;
    font-family: 'Gilroy-Regular', sans-serif;

}
.steps__question {
    margin-top: 0;
    margin-bottom: 10px;
    color: #3A3A3A;
    font-family: 'Gilroy-Bold', sans-serif;
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
    font-family: 'Gilroy-Medium', sans-serif;
    width: 100%;
    margin: 0;
    margin-bottom: 1rem;
}
textarea {
    resize: vertical;
    margin-bottom: 0;
}
/* CUSTOM DROPDOWN MENU (SELECT) */
div[data-type='select'] {
    position: relative;
    margin-bottom: 1rem;
}
div[data-type='select']::after {
    content: url("../assets/icons/chevron_dark.png");
    position: absolute;
    top: 50%;
    right: 3rem;
    transform: translateY(-50%);
    cursor: pointer;
    pointer-events:revert;
    z-index: -1;
}
div[data-type='select'] select {
    padding: 1.25rem 2.5rem;
    font-size: 1rem;
    border: 1px solid #c4c4c4;
    width: 366px;
    height: 68px;
     margin: 0;
    appearance: none;
    cursor: pointer;
    outline: none;
    font-family: 'Gilroy-Medium', sans-serif;
    background-color: transparent;

}
div[data-type='select'] select option {
    color: #3A3A3A;
}
div[data-type='select'] select[data-placeholder-selected] {
    color: #999999;
}

/* ADD & REMOVE FORM ELEMENTS - BUTTONS STYLING */
.formulate-input-group-add-more {
    text-align: right;

}
.formulate-input-group-add-more button {
    color:#FF0083;
    padding-right: 0;
    font-family: 'Gilroy-SemiBold', sans-serif;
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
    font-family: 'Gilroy-SemiBold', sans-serif;
    line-height: 19px;
}
.formulate-input-group-repeatable-remove::after {
    content: url(../assets/icons/trash.png) ' Verwijder';
    visibility: visible;
    color: #898989;
    font-size: 1rem;

}
.formulate-input-group-repeatable:first-of-type .formulate-input-group-repeatable-remove {
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
    background-color: #F0F0F0;
    display: inline-flex;
    justify-content: center;
    align-items: center;
}
.checkbox-container input[type="radio"],
.checkbox-container input[type="checkbox"] {
    display: none;
}
.checkbox-container input[type="radio"]:checked + label::after,
.checkbox-container input[type="checkbox"]:checked + label::after {
    content: url(../assets/icons/correct.png)
}
.checkbox-label {
     font-family: 'Gilroy-Bold', sans-serif;
     font-size: 1rem;
     white-space: nowrap;
     color: #3A3A3A;
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
</style>
