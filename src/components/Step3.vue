<template>
    <div class="container step-3">
        <h1 class="steps__title bold">
            Bereken eenvoudig de kosten met onze tool
        </h1>
        <div class="flex">
            <StepsProgressBar :step="3" />
            <div class="steps__form">
                <h3 class="steps__no">Stap 3</h3>
                <h2 class="steps__question">Kies bijpassende raamdecoratie</h2>
                <p class="steps__help">
                    Wil je van de montagepartner ook prijzen ontvangen van VELUX
                    raamdecoratie?
                </p>
                <FormulateForm v-model="formData">
                    <FormulateInput
                        type="radio"
                        element-class="checkbox-container"
                        label-class="checkbox-label"
                        validation="required"
                        name="window decoration"
                        :options="{
                            Ja: 'Ja',
                            Nee: 'Nee',
                        }"
                    />
                    <div v-if="formData['window decoration'] == 'Ja'">
                        <div
                            class="flex border-top decoration-container"
                            id="decoration-container"
                            v-for="(decoration, index) in window_decoration"
                            :key="decoration+index"
                        >
                            <FormulateInput
                                type="checkbox"
                                :name="decoration+index"
                                element-class="checkbox-container"
                                :id="decoration+index"
                            />
                            <label :for="decoration+index" class="decoration flex"
                                ><img src="../assets/icons/window.png" />
                                <h3>{{ decoration }}</h3></label
                            >
                        </div>
                    </div>
                </FormulateForm>
                <NavigationBtns :btnActive="Object.keys(formData).length ? true : false" proceed="Step4" back="Step2" />

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
            window_decoration: [
                "VELUX Verduisterende rolgordijnen",
                "VELUX Verduisterend rolgordijn + plissé",
                "VELUX insectenhor",
                "VELUX Jaloezie",
                "VELUX Lichtdoorlatend plissé",
                "VELUX Lichtdoorlatend rolgordijn",
                "VELUX Lichtdoorlatend rolgordijn",
                "VELUX Lichtdoorlatend rolgordijn",
                "VELUX Lichtdoorlatend rolgordijn"
            ],
        };
    },
    activated() {
        window.scroll({
            top: 0,
            left: 0,
        });
    },
};
</script>

<style>
.steps__help {
    color: #616161;
}
#decoration-container {
    padding: 1.5rem 0;
    gap: 0;
    flex-direction: row;
}
.decoration-container .decoration {
    flex-direction: row;
}
.decoration h3 {
    font-family: "Gilroy-Semibold", sans-serif;
    max-width: 20ch;
    width: 100%;
}
.decoration img {
    border: 1px solid #f4f5f7;
    margin-left: 1.8rem;
}

@media only screen and (max-width: 768px) {
    .decoration img {
        max-width: 70px;
        max-height: 70px;
        margin: 0 1rem;
    }
}
</style>
