<template>
    <div class="thankyou">
        <div class="container">
            <h1 class="thankyou__title font-Bold">
                Jouw aanvraag is succesvol verzonden!
            </h1>
            <p class="thankyou__subtitle">
                Slim dat je kiest voor officiële montagepartners van VELUX, met
                10 jaar garantie op de montage en producten.
            </p>
            <button class="thankyou__CTA primary-btn">
                Terug naar homepage
            </button>
        </div>
    </div>
</template>

<script>
export default {};
</script>

<style>
.thankyou .container {
    text-align: center;
    background-image: url("../assets/icons/watermark.png");
    background-repeat: no-repeat;
    background-size: 270px 291px;
    background-position: top;
    padding-top: 7rem;
}
.thankyou__title {
    color: #ff0083;
    font-size: calc(26px + (40 - 26) * ((100vw - 300px) / (1600 - 300)));
    line-height: 48px;
    max-width: 25ch;
    margin: 0.9rem auto;
}
.thankyou__subtitle {
    color: #8f999e;
    font-size: 18px;
    line-height: 22px;
    max-width: 45ch;
    margin: 0 auto;
    font-family: "Gilroy-Medium", sans-serif;
}
.thankyou__CTA {
    padding: 1rem 2.9rem;
    font-size: 1rem;
    font-family: "Gilroy-SemiBold", sans-serif;
    margin-top: 3.8rem;
}

@media only screen and (max-width: 768px) {
    .thankyou__title {
        line-height: 30px;
        max-width: 20ch;
    }
    .thankyou__subtitle {
        max-width: 30ch;
        font-size: 1rem;
    }
    .thankyou .container {
        background-size: 141px 161px;
        padding-top: 0;
    }
    .thankyou__CTA {
        width: 100%;
    }
}
</style>
