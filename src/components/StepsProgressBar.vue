<template>
    <div class="progressBar">
        <div
            v-for="n in 4"
            :key="n"
            class="progressBarStep"
            :class="[n <= step ? 'complete' : '', n == step ? 'active' : '']"
        ></div>
    </div>
</template>

<script>
export default {
    props: {
        step: {
            type: Number,
            required: true,
            default: 1,
        },
    },
};
</script>

<style>
.progressBar {
    display: flex;
    flex-direction: column;
    gap: 2.3rem;
    margin: 0 5rem;
    counter-reset: steps;
}

.progressBarStep {
    height: 40px;
    width: 40px;
    background-color: #e4e4e4;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-size: 1.5rem;
    box-sizing: border-box;
    position: relative;
}
.progressBarStep.complete {
    background-color: #ff0083;
}
.progressBarStep.active {
    border: 4px solid white;
    outline: 1px solid #ff0083;
    padding: 1.1rem;
}
.progressBarStep::before {
    counter-increment: steps;
    content: counter(steps);
}
.progressBarStep:not(:last-of-type)::after {
    position: absolute;
    content: "";
    top: 100%;
    height: 2.5rem;
    width: 1px;
    background-color: #e4e4e4;
    z-index: -1;
}
.progressBarStep.complete:not(:last-of-type)::after {
    background-color: #ff0083;
}

@media only screen and (max-width: 768px) {
    .progressBar {
        flex-direction: row;
        margin: 0;
        margin-top: 3.1rem;
        margin-bottom: 2.1rem;
    }
    .progressBarStep {
        width: 50px;
        height: 50px;
    }
    .progressBarStep:not(:last-of-type)::after {
        position: absolute;
        content: "";
        left: 100%;
        top: 50%;
        transform: translateY(-50%);
        width: 2.5rem;
        height: 1px;
        background-color: #e4e4e4;
        z-index: -1;
    }
}
</style>
