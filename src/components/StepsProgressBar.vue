<template>
  <div class="progressBar">
      <div v-for="n in 4" :key="n" class="progressBarStep" :class="[n <= step ? 'complete' : '', n == step ? 'active' : '']"></div>
  </div>
</template>

<script>
export default {
    props: ['step']
}
</script>

<style>
.progressBar {
    display: flex;
    flex-direction: column;
    gap: 2.3rem;
    margin: 0 5rem;
    counter-reset: steps;
    box-sizing: content-box;
}

.progressBarStep {
    height: 40px;
    width: 40px;
    background-color: #E4E4E4;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-size: 1.5rem;
    position: relative;

    /* outline-offset: 0.25rem; */

}
.progressBarStep.complete {
    background-color: #FF0083;


}
.progressBarStep.active {
    outline-color: #FF0083;
     border: .3rem solid white;
     outline: 1px solid #FF0083;
     padding: 1rem;
}
.progressBarStep::before {
    counter-increment: steps;
    content: counter(steps)
}
.progressBarStep:not(:last-of-type)::after {
    position: absolute;
    content: '';
    top:100%;
    height: 2.5rem;
    width: 1px;
    background-color: #E4E4E4;
    z-index: -1;
}
.progressBarStep.complete:not(:last-of-type)::after {
    background-color: #FF0083;
    /* top:110%;
    height: 2.5rem; */
}
</style>