<template>
  <div class="container step-2">
    <h1 class="steps__title">Bereken eenvoudig de kosten met onze tool</h1>
    <div class="flex">
      <StepsProgressBar :step="2" />
      <div class="steps__form">
        <h3 class="steps__no">Stap 2</h3>
        <h2 class="steps__question">Vind een montagepartner</h2>
        <p class="steps__help">
          Geef hieronder aan waar jouw gekozen VELUX oplossing(en) gemonteerd
          moeten worden.
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
          <div
            class="flex partners border-top"
            id="partners"
            v-for="partner in getPartners"
            :key="partner.Name"
          >
            <FormulateInput
              type="checkbox"
              :name="partner.Name"
              element-class="checkbox-container"
              :id="partner.Name"
            />
            <label :for="partner.Name" class="partner"
              ><h3>{{ partner.Name }}</h3>
              <div class="flex">
                {{ partner.Rating }}
                <!-- <img src="../assets/icons/stars.png" alt="" /> -->
                <ul class="rating flex justify-center mb-0">
                  <li v-for="i in 5" :key="i">

                    <svg
                      v-if="i <= Math.floor(partner.Rating)"
                      aria-hidden="true"
                      focusable="false"
                      data-prefix="fas"
                      data-icon="star"
                      style="width:1rem; color:#eab308"

                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 576 512"
                    >
                      <path
                        fill="currentColor"
                        d="M259.3 17.8L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0z"
                      ></path>
                    </svg>

                    <svg
                    v-else-if="!Number.isInteger(partner.Rating) && i == Math.ceil(partner.Rating)"
                      aria-hidden="true"
                      focusable="false"
                      data-prefix="fas"
                      data-icon="star-half-alt"
                      style="width:1rem; color:#eab308"
                      role="img"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 536 512"
                    >
                      <path
                        fill="currentColor"
                        d="M508.55 171.51L362.18 150.2 296.77 17.81C290.89 5.98 279.42 0 267.95 0c-11.4 0-22.79 5.9-28.69 17.81l-65.43 132.38-146.38 21.29c-26.25 3.8-36.77 36.09-17.74 54.59l105.89 103-25.06 145.48C86.98 495.33 103.57 512 122.15 512c4.93 0 10-1.17 14.87-3.75l130.95-68.68 130.94 68.7c4.86 2.55 9.92 3.71 14.83 3.71 18.6 0 35.22-16.61 31.66-37.4l-25.03-145.49 105.91-102.98c19.04-18.5 8.52-50.8-17.73-54.6zm-121.74 123.2l-18.12 17.62 4.28 24.88 19.52 113.45-102.13-53.59-22.38-11.74.03-317.19 51.03 103.29 11.18 22.63 25.01 3.64 114.23 16.63-82.65 80.38z"
                      ></path>
                    </svg>
                    <svg
                      v-else
                      aria-hidden="true"
                      focusable="false"
                      data-prefix="far"
                      data-icon="star"
                      style="width:1rem; color:#eab308"
                      role="img"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 576 512"
                    >
                      <path
                        fill="currentColor"
                        d="M528.1 171.5L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6zM388.6 312.3l23.7 138.4L288 385.4l-124.3 65.3 23.7-138.4-100.6-98 139-20.2 62.2-126 62.2 126 139 20.2-100.6 98z"
                      ></path>
                    </svg>
                  </li>
                </ul>
                (148) | 1.7 km <br />

              </div>
              <div>
                {{ partner.City }}<br />
                Gemiddelde responstijd:{{ partner["Average response time"] }}
              </div>
              </label
            >
          </div>
        </FormulateForm>
        <button class="show-more-btn" @click="partnersToShow += 10">
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
      partnersToShow: 10,
      partners: [
        {
          Name: "Dakraam Vervangservice",
          City: "Leiderdorp",
          partner_response: " Gemiddelde responstijd: binnen een dag",
        },
        {
          Name: "Bendabouw Geveltechniek",
          City: "Nootdorp",
          partner_response: "Gemiddelde responstijd: 6 dagen",
        },
      ],
    };
  },
  activated() {
    window.scroll({
      top: 0,
      left: 0,
    });
    this.fetchPartners();
  },

  methods: {
    async fetchPartners() {
      const partners = await require("../assets/Montage-partners-info.json");
      //    const data = await fetch('../assets/Montage-partners-info.json')
      // const res = await data.json()
      this.partners = partners.Sheet1;
    },

  },
  computed: {
    getPartners() {
      return this.partners.slice(0, this.partnersToShow);
    },
  },
};
</script>

<style>
.partners .formulate-input-group-item {
  border-top: 1px solid #e4e4e4;
  padding: 1.25rem 0;
  width: 100%;
}
#partners {
  padding: 1.25rem 0;
  flex-direction: row;
  gap: 1rem;
}
.partners .checkbox-container {
  margin-top: 0;
  gap: 1.5rem;
}
.partner .flex {
  align-items: center;
  margin: 5px 0;
  flex-direction: row;
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
  display: inline;
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
.rating {
  gap: 0rem !important;
  padding: 0;
  list-style: none;
}

</style>
