<template>
    <div class="container step-4">
        <h1 class="steps__title bold">
            Bereken eenvoudig de kosten met onze tool
        </h1>
        <div class="flex">
            <StepsProgressBar :step="4" />
            <div class="steps__form">
                <h3 class="steps__no">Stap 4</h3>
                <h2 class="steps__question">Jouw contactinformatie</h2>

                <FormulateForm v-model="formData" @submit="send">
                    <FormulateInput
                        name="firstname"
                        placeholder="Voornaam"
                        validation="required"
                    />
                    <FormulateInput
                        name="lastname"
                        placeholder="Achternaam"
                        validation="required"
                    />
                    <FormulateInput
                        name="telephone"
                        placeholder="Telefoonnummer"
                        type="tel"
                        validation="required"
                    />
                    <FormulateInput
                        name="email"
                        placeholder="E-mailadres"
                        type="email"
                        validation="bail|required|email"
                    />
                    <FormulateInput
                        type="textarea"
                        name="message"
                        rows="4"
                        placeholder="Voeg een bericht toe (niet verplicht)"
                    />
                    <FormulateInput
                        type="submit"
                        value="submit"
                        element-class="proceed-btn"
                    />
                </FormulateForm>
                <NavigationBtns
                    proceed="ThankYou"
                    back="Step3"
                    proceedBtnValue="Aanvraag versturen"
                />
            </div>
        </div>
    </div>
</template>

<script>
import StepsProgressBar from "./StepsProgressBar.vue";
import NavigationBtns from "./NavigationBtns.vue";
export default {
    components: {
        StepsProgressBar,
        NavigationBtns,
    },
    data() {
        return {
            formData: {},
        };
    },
    methods: {
        send() {
            console.log("submitted");
        },
    },
    activated() {
        window.scroll({
            top: 0,
            left: 0,
        });
    },
};
</script>

<style></style>
