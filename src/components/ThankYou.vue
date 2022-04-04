<template>
  <div class="thankyou">
      <div class="container">
          <h1 class="thankyou__title font-Bold">Jouw aanvraag is succesvol verzonden!</h1>
          <p class="thankyou__subtitle">Slim dat je kiest voor officiële montagepartners van VELUX, met 10 jaar garantie op de montage en producten.</p>
          <button class="thankyou__CTA primary-btn">Terug naar homepage</button>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.thankyou .container {
    text-align: center;
    background-image: url('../assets/icons/watermark.png');
    background-repeat: no-repeat;
    background-size: 270px 291px;
    background-position: top;
    padding-top: 7rem;
}
.thankyou__title {
    color: #FF0083;
    font-size: 40px;
    line-height: 48px;
    max-width: 25ch;
    margin: 0.9rem auto;
}
.thankyou__subtitle {
    color: #8F999E;
    font-size: 18px;
    line-height: 22px;
    max-width: 45ch;
    margin: 0 auto;
    font-family: 'Gilroy-Medium', sans-serif;
}
.thankyou__CTA {
    padding: 0.75rem 2.9rem;
    font-size: 1rem;
    font-family: 'Gilroy-SemiBold', sans-serif;
    margin-top: 3.8rem;
}
</style>