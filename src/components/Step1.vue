<template>
    <div class="container step-1">
        <h1 class="steps__title">Bereken eenvoudig de kosten met onze tool</h1>
        <div class="flex">
            <StepsProgressBar :step="1" />
            <div class="steps__form">
                <h3 class="steps__no">Stap 1</h3>
                <h2 class="steps__question">Welk type montage?</h2>
                <Accordion :formData="formData['Dakraam plaatsen']">
                    <template v-slot:title>
                        <span>Dakraam plaatsen</span>
                    </template>
                    <template v-slot:content>
                        <div class="form-wrapper">
                            <FormulateForm v-model="formData">
                                <FormulateInput
                                    type="group"
                                    name="Dakraam plaatsen"
                                    :repeatable="true"
                                    add-label="+ Voeg dakraam toe"
                                    validation="min:1,required"
                                >
                                    <FormulateInput
                                        type="select"
                                        name="Type dakraam"
                                        placeholder="Type dakraam"
                                        :options="{
                                            Tuimelvenster: 'Tuimelvenster',
                                        }"
                                    />
                                    <FormulateInput
                                        type="select"
                                        name="Maat (b x h)"
                                        placeholder="Maat (b x h)"
                                        :options="{
                                            'CK02 (55 x 78)': 'CK02 (55 x 78)',
                                        }"
                                    />
                                    <FormulateInput
                                        type="select"
                                        name="Aantal"
                                        placeholder="Aantal"
                                        :options="{ 1: 1 }"
                                    />
                                </FormulateInput>
                                <FormulateInput
                                    type="radio"
                                    element-class="checkbox-container"
                                    label-class="checkbox-label"
                                    validation="required"
                                    name="Aftimmering binnenzijde?"
                                    label="Aftimmering binnenzijde?"
                                    :options="{
                                        Ja: 'Ja',
                                        Nee: 'Nee',
                                    }"
                                />
                            </FormulateForm>
                        </div>
                    </template>
                </Accordion>

                <Accordion :formData="formData['VELUX dakraam vervangen']">
                    <template v-slot:title>
                        <span>VELUX dakraam vervangen</span>
                    </template>
                    <template v-slot:content>
                        <div class="form-wrapper">
                            <FormulateForm v-model="formData">
                                <FormulateInput
                                    type="group"
                                    name="VELUX dakraam vervangen"
                                    :repeatable="true"
                                    add-label="+ Voeg dakraam toe"
                                    validation="min:1,required"
                                >
                                    <FormulateInput
                                        type="select"
                                        name="Code oude dakraam"
                                        placeholder="Code oude dakraam"
                                        :options="{
                                            Tuimelvenster: 'Tuimelvenster',
                                        }"
                                    />
                                    <FormulateInput
                                        type="select"
                                        name="Gewenst type nieuw dakraam"
                                        placeholder="Gewenst type nieuw dakraam"
                                        :options="{
                                            'CK02 (55 x 78)': 'CK02 (55 x 78)',
                                        }"
                                    />
                                    <FormulateInput
                                        type="select"
                                        name="Aantal"
                                        placeholder="Aantal"
                                        :options="{ 1: 1 }"
                                    />
                                </FormulateInput>
                            </FormulateForm>
                        </div>
                    </template>
                </Accordion>
                <Accordion :formData="formData['Niet-VELUX dakraam vervangen']">
                    <template v-slot:title>
                        <span>Niet-VELUX dakraam vervangen</span>
                    </template>
                    <template v-slot:content>
                        <div class="form-wrapper" id="form-wrapper">
                            <p class="gray">Maten oude dakraam (b x h), cm</p>
                            <FormulateForm v-model="formData">
                                <FormulateInput
                                    type="group"
                                    name="Niet-VELUX dakraam vervangen"
                                    :repeatable="true"
                                    add-label="+ Voeg dakraam toe"
                                    validation="min:1,required"
                                >
                                    <div class="flex">
                                        <FormulateInput
                                            type="number"
                                            name="breadth"
                                            placeholder="cm"
                                        />
                                        <FormulateInput
                                            type="number"
                                            name="height"
                                            placeholder="cm"
                                        />
                                    </div>
                                    <FormulateInput
                                        type="select"
                                        name="Gewenst type nieuw dakraam"
                                        placeholder="Gewenst type nieuw dakraam"
                                        :options="{
                                            Tuimelvenster: 'Tuimelvenster',
                                        }"
                                    />
                                    <FormulateInput
                                        type="select"
                                        name="Maat nieuwe dakraam (b x h)"
                                        placeholder="Maat nieuwe dakraam (b x h)"
                                        :options="{
                                            'CK02 (55 x 78)': 'CK02 (55 x 78)',
                                        }"
                                    />
                                    <FormulateInput
                                        type="select"
                                        name="Aantal"
                                        placeholder="Aantal"
                                        :options="{ 1: 1 }"
                                    />
                                </FormulateInput>
                            </FormulateForm>
                        </div>
                    </template>
                </Accordion>
                <FormulateInput
                    type="radio"
                    element-class="checkbox-container"
                    :label-class="['checkbox-label', 'border-top']"
                    validation="required"
                    v-model="
                        formData[
                            'Wil je dat wij het oude dakraam + verpakkingsmateriaal afvoeren?'
                        ]
                    "
                    name="Wil je dat wij het oude dakraam + verpakkingsmateriaal afvoeren?"
                    label="Wil je dat wij het oude dakraam + verpakkingsmateriaal afvoeren?"
                    :options="{
                        Ja: 'Ja',
                        Nee: 'Nee',
                    }"
                />
                <div class="total flex border-top" id="total">
                    <div class="total__text">
                        <h2>Geschatte prijs:</h2>
                        <p class="gray">
                            incl. montage, voorrijkosten en <br />
                            BFX (waterkerend manchet)
                        </p>
                    </div>
                    <div class="total__price">
                        <h1>€ 1159,00</h1>
                    </div>
                </div>
                <NavigationBtns proceed="Step2" back="Home" />
            </div>
        </div>
    </div>
</template>

<script>
import Accordion from "./Accordion.vue";
import StepsProgressBar from "./StepsProgressBar.vue";
import NavigationBtns from "./NavigationBtns.vue";
export default {
    components: {
        Accordion,
        StepsProgressBar,
        NavigationBtns,
    },
    data() {
        return {
            formData: {
                "Aftimmering binnenzijde?": "Ja",
                "Wil je dat wij het oude dakraam + verpakkingsmateriaal afvoeren?":
                    "Ja",
            },
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
.container {
    margin: 0 auto;
}

.steps__form {
    margin-top: 2.5rem;
    max-width: 400px;
    width: 100%;
}

.checkbox_container p {
    white-space: nowrap;
}
.checkbox {
    flex: 1;
}
.checkbox label {
    padding-left: 0.5rem;
}

.total {
    justify-content: space-between;
    align-items: center;
    flex-direction: row;
}
.total__text h2 {
    margin-bottom: 0;
    margin-top: 1.8rem;
    font-size: calc(20px + (24 - 20) * ((100vw - 300px) / (1600 - 300)));
}
.total__text p {
    margin-top: 0.3rem;
    color: #999999;
    font-size: 14px;
    line-height: 21px;
}
.total__price h1 {
    font-size: calc(26px + (36 - 26) * ((100vw - 300px) / (1600 - 300)));
    color: #ff0083;
    font-family: "Gilroy-Bold", sans-serif;
}

.back-btn img {
    transform: rotate(180deg);
}

@media only screen and (max-width: 768px) {
    .steps__form {
        margin-top: 0;
    }
    #total,
    #form-wrapper .flex {
        flex-direction: row;
    }
}
</style>
