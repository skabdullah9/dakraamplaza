<template>
    <div class="container step-2">
        <h1 class="steps__title">
            Bereken eenvoudig de kosten met onze tool
        </h1>
        <div class="flex">
            <StepsProgressBar :step="2" />
            <div class="steps__form">
                <h3 class="steps__no">Stap 2</h3>
                <h2 class="steps__question">Vind een montagepartner</h2>
                <p class="steps__help">
                    Geef hieronder aan waar jouw gekozen VELUX oplossing(en)
                    gemonteerd moeten worden.
                </p>
                <FormulateForm v-model="formData">
                    <FormulateInput
                        name="postcode"
                        placeholder="postcode"
                        validation="required"
                    />
                    <FormulateInput
                        name="Huisnummer"
                        placeholder="Huisnummer"
                        validation="required"
                    />
                    <div class="flex partners border-top" v-for="partner in partners" :key="partner.partner_name">
                        <FormulateInput
                            type="checkbox"
                            :name="partner.partner_name"
                            element-class="checkbox-container"
                            :id="partner.partner_name"
                        />
                        <label :for="partner.partner_name" class="partner"><h3>{{partner.partner_name}}</h3><div class="flex">4.7 <img src="../assets/icons/stars.png" alt=""> (148) | 1.7 km</div><div>{{partner.partner_location}}<br>{{partner.partner_response}}</div></label>
                    </div>
                </FormulateForm>
                <button class="show-more-btn">
                    Toon meer
                    <img src="../assets/icons/chevron_pink.png" alt="" />
                </button>
                <p class="show-more-help">
                    Wij adviseren u één of maximaal twee partners te selecteren.
                </p>

                <NavigationBtns proceed="Step3" back="Step1" />
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
            partners: [
                {partner_name: "Dakraam Vervangservice", partner_location: 'Leiderdorp', partner_response: " Gemiddelde responstijd: binnen een dag"},
                 {partner_name: "Bendabouw Geveltechniek", partner_location: 'Nootdorp', partner_response: "Gemiddelde responstijd: 6 dagen"}
            ]
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


.partners .formulate-input-group-item {
    border-top: 1px solid #e4e4e4;
    padding: 1.25rem 0;
    width: 100%;
}
.partners {
    padding: 1.25rem 0;
    flex-direction: row !important;
    gap: 1rem !important;
}
.partners .checkbox-container {
    margin-top: 0;
    gap: 1.5rem;
}
.partner .flex {
    align-items: center;
    margin: 5px 0;
    flex-direction: row ;
}
.partner h3 {
    margin-top: 0;
    margin-bottom: 5px;
    font-family: "Gilroy-Semibold", sans-serif;
}
.partner > div {
    color: #898989;
    font-size: 14px;
}
.show-more-btn {
    color: #ff0083;
    font-size: 1rem;
    font-family: "Gilroy-Semibold", sans-serif;
    padding-left: 0;
}
.show-more-btn img {
    height: 10px;
    margin-left: 5px;
    transform: rotate(90deg);
}
.show-more-help {
    color: #898989;
    white-space: nowrap;
    font-size: 1rem;
    font-family: "Gilroy-Regular", sans-serif;
    margin-bottom: 0;
}
</style>
