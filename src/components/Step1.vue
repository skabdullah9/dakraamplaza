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
                      Uitzettuimelvenster: 'Uitzettuimelvenster',
                      '2-in-1 (tuimel)': '2-in-1 (tuimel)',
                      '2-in-1 (uitzettuimel)': '2-in-1 (uitzettuimel)',
                      '3-in-1 (tuimel)': '3-in-1 (tuimel)',
                      '3-in-1 (uitzettuimel)': '3-in-1 (uitzettuimel)',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Materiaal"
                    placeholder="Materiaal"
                    :options="{
                      'Grenenhout, wit afgelakt': 'Grenenhout, wit afgelakt',
                      'Grenenhout, blank afgelakt':
                        'Grenenhout, blank afgelakt',
                      'Kunststof, wit gelakt': 'Kunststof, wit gelakt',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Glastype"
                    placeholder="Glastype"
                    :options="{
                      '66 top comfort': '66 top comfort',
                      '68 extra comfort': '68 extra comfort',
                      '70 comfort (standaard)': '70 comfort (standaard)',
                      '69 warmtewerend': '69 warmtewerend',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Bediening"
                    placeholder="Bediening"
                    :options="{
                      Handbediend: 'Handbediend',
                      'Elektrisch (netstroom)': 'Elektrisch (netstroom)',
                      'Zonne-energie': 'Zonne-energie',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Maat (b x h)"
                    placeholder="Maat (b x h)"
                    :options="{
                      'CK01 (55 x 70)': 'CK01 (55 x 70)',
                      'CK02 (55 x 78)': 'CK02 (55 x 78)',
                      'CK04 (55 x 98)': 'CK04 (55 x 98)',
                      'CK06 (55 x 118)': 'CK06 (55 x 118)',
                      'FFK06 (127 x 118)': 'FFK06 (127 x 118)',
                      'FFK08 (127 x 140)': 'FFK08 (127 x 140)',
                      'FFKF06 (188 x 118)': 'FFKF06 (188 x 118)',
                      'FFKF08 (188 x 140)': 'FFKF08 (188 x 140)',
                      'FK04 (66 x 98)': 'FK04 (66 x 98)',
                      'FK06 (66 x 118)': 'FK06 (66 x 118)',
                      'FK08 (66 x 140)': 'FK08 (66 x 140)',
                      'FMK06 (139 x 118)': 'FMK06 (139 x 118)',
                      'FMK08 (139 x 140)': 'FMK08 (139 x 140)',
                      'FPK06 (94 x 118) (155 x 118)':
                        'FPK06 (94 x 118) (155 x 118)',
                      'FPK08 (94 x 140) (155 x 140)':
                        'FPK08 (94 x 140) (155 x 140)',
                      'MK04 (78 x 98)': 'MK04 (78 x 98)',
                      'MK06 (78 x 118)': 'MK06 (78 x 118)',
                      'MK08 (78 x 140)': 'MK08 (78 x 140)',
                      'MK10 (78 x 160)': 'MK10 (78 x 160)',
                      'MK12 (78 x 180)': 'MK12 (78 x 180)',
                      'MMK06 (151 x 118)': 'MMK06 (151 x 118)',
                      'MMK08 (151 x 140)': 'MMK08 (151 x 140)',
                      'PK04 (94 x 98)': 'PK04 (94 x 98)',
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
                      '425, P25': '425, P25',
                      '601, S01': '601, S01',
                      '4, 606, S06': '4, 606, S06',
                      '10, 608, S08': '10, 608, S08',
                      '7, 804, U04': '7, 804, U04',
                      '74, U06': '74, U06',
                      '8, 808, U08': '8, 808, U08',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Gewenste maat (b x h)"
                    placeholder="Gewenste maat (b x h)"
                    :options="{
                      'CK02 (55 x 78)': 'CK02 (55 x 78)',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Gewenst type"
                    placeholder="Gewenst type"
                    :options="{
                      'CK02 (55 x 78)': 'CK02 (55 x 78)',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Gewenst materiaal"
                    placeholder="Gewenst materiaal"
                    :options="{
                      'CK02 (55 x 78)': 'CK02 (55 x 78)',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Gewenst glastype"
                    placeholder="Gewenst glastype"
                    :options="{
                      'CK02 (55 x 78)': 'CK02 (55 x 78)',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Gewenste bediening"
                    placeholder="Gewenste bediening"
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
                    name="Gewenste maat"
                    placeholder="Gewenste maat"
                    :options="{
                      Tuimelvenster: 'Tuimelvenster',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Gewenst type"
                    placeholder="Gewenst type"
                    :options="{
                      'CK02 (55 x 78)': 'CK02 (55 x 78)',
                    }"
                  />
                  <FormulateInput
                    type="select"
                    name="Gewenst materiaal"
                    placeholder="Gewenst materiaal"
                    :options="{ 1: 1 }"
                  />
                  <FormulateInput
                    type="select"
                    name="Gewenst glastype"
                    placeholder="Gewenst glastype"
                    :options="{ 1: 1 }"
                  />
                  <FormulateInput
                    type="select"
                    name="Gewenste bediening"
                    placeholder="Gewenste bediening"
                    :options="{ 1: 1 }"
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

        <div
          v-show="renderPrice"
          class="total flex border-top"
          id="total"
        >
          <div class="total__text">
            <h2>Geschatte prijs:</h2>
            <p class="gray">
              incl. montage, voorrijkosten en <br />
              BFX (waterkerend manchet)
            </p>
          </div>
          <div class="total__price">
            <h1>€ {{ renderPrice.toFixed(2) }}</h1>
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
      formData: {},
      allValues: [],
      selectedObjects: []
    };
  },
  activated() {
    window.scroll({
      top: 0,
      left: 0,
    });
    this.getJsonValues();
  },
  computed: {
    renderPrice() {
      this.getPrice()
      return this.selectedObjects.reduce((acc, val) => acc + val['Price'], 0)
    }
  },
  methods: {
    getJsonValues() {
      const jsonData = require("../assets/Values-Configurator-2022.json");
      this.allValues = jsonData;
      console.log(this.allValues);
      return jsonData;
    },
    getPrice() {
      let formDetails = JSON.parse(JSON.stringify(this.formData));
      console.log(formDetails["Dakraam plaatsen"]);
      if(!formDetails['Dakraam plaatsen']) return false
      let targetObj = this.allValues.find(
        (obj) =>
          obj["Type dakraam"] ==
          formDetails["Dakraam plaatsen"][formDetails["Dakraam plaatsen"].length - 1]["Type dakraam"] &&
          obj["Materiaal"] ==
          formDetails["Dakraam plaatsen"][formDetails["Dakraam plaatsen"].length - 1]["Materiaal"] &&
          obj["Glastype"] ==
          formDetails["Dakraam plaatsen"][formDetails["Dakraam plaatsen"].length - 1]["Glastype"] &&
          obj["Bediening"] ==
          formDetails["Dakraam plaatsen"][formDetails["Dakraam plaatsen"].length - 1]["Bediening"]
      );

      if(targetObj) {
        this.selectedObjects.push(targetObj)
      }
        console.log(targetObj, JSON.parse(JSON.stringify(this.selectedObjects)));

    }
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
