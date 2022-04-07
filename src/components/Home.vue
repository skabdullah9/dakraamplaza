<template>
    <div class="home">
        <div class="container flex">
            <div class="left">
                <h2>De zekerheden van de VELUX montagepartner</h2>
                <img src="../assets/icons/Checkmark.png" alt="" />
                <p>
                    Je ontvangt deskundig advies, vrijblijvende offertes en
                    professionele hulp bij de aankoop en montage
                </p>
                <img src="../assets/icons/Checkmark.png" alt="" />
                <p>
                    De montagepartner heeft minimaal 2 jaar ervaring met het
                    monteren van VELUX producten
                </p>
                <img src="../assets/icons/Checkmark.png" alt="" />
                <p>
                    Elke VELUX montagepartner volgt minimaal 1 keer per jaar een
                    training bij VELUX Nederland
                </p>
            </div>
            <div class="right">
                <h1>De VELUX Montageservice, zo eenvoudig werkt het</h1>
                <div class="steps">
                    <div class="step__one flex">
                        <h1>01</h1>
                        <p class="font-bold">
                            Kies het product waar je interesse in hebt
                        </p>
                    </div>
                    <div class="step__two flex border-top">
                        <h1>02</h1>
                        <div>
                            <p class="font-bold">
                                Vul jouw postcode in en selecteer één of twee
                                montagepartners bij jou in de buurt
                            </p>
                            <small
                                ><span class="font-semibold">Let op!</span>
                                VELUX montagepartners zijn geen werknemers van
                                Dakraamplaza, maar aannemers die door VELUX
                                getraind en gecertificeerd worden. In deze stap
                                selecteer je maximaal twee montagepartners om
                                contact met je op te nemen.</small
                            >
                        </div>
                    </div>
                    <div class="step__three flex border-top">
                        <h1>03</h1>
                        <p class="font-bold">
                            Kies bijpassende raamdecoratie (niet verplicht)
                        </p>
                    </div>
                    <div class="step__four flex border-top">
                        <h1>04</h1>
                        <div>
                            <p class="font-bold">
                                De geselecteerde montagepartners nemen contact
                                met je op via de telefoon of e-mail
                            </p>
                            <small
                                ><span class="font-semibold">Let op!</span> Wij
                                streven streeft ernaar dat onze montagepartners
                                binnen 5 werkdagen contact met je opnemen. In
                                verband met drukte kan dit afwijken en langer
                                duren. Dakraamplaza heeft geen invloed op
                                genoemde montageprijzen en geeft slechts
                                richtprijzen.</small
                            >
                        </div>
                    </div>
                </div>
                <button
                    class="steps__CTA primary-btn"
                    @click="$emit('changeComponent', 'Step1')"
                >
                    Vind een montagepartner
                    <img src="../assets/icons/chevron_down.png" alt="" />
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {};
</script>

<style>
.home,
.thankyou {
    display: grid;
    place-items: center;
    min-height: 100vh;
    overflow: hidden;
}

.left {
    background: url("../assets/img/BG.png");
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    color: white;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 0 2rem;
    height: 100vh;
}
.left p {
    max-width: 30ch;
    font-family: "Gilroy-Regular", sans-serif;
    margin: 1rem auto 2rem;
    line-height: 1.5;
    font-size: 18px;
}
.left h2 {
    line-height: 1.3;
    font-family: "Gilroy-Bold", sans-serif;
    max-width: 22ch;
    margin-bottom: 2.5rem;
}

.right {
    padding: 1.8rem 4rem;
}
.right > h1 {
    max-width: 30ch;
    font-size: calc(26px + (40 - 26) * ((100vw - 300px) / (1600 - 300)));
    font-family: "Gilroy-Bold", sans-serif;
}
.steps > div {
    align-items: center;
    margin: 0 auto;
    line-height: 1.3;
}
.steps h1 {
    color: #ff0083;
    font-size: min(12vw, 2.75rem);
    min-width: 100px;
    font-family: "Gilroy-Bold", sans-serif;
}
.steps p {
    font-size: 1rem;
    max-width: 54ch;
}
.steps small {
    font-size: 14px;
    font-family: "Gilroy-Regular", sans-serif;
    max-width: 63ch;
    display: block;
}
.steps__CTA {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.8rem 3.1rem;
    margin-top: 3.1rem;
    font-size: 1rem;
    font-family: "Gilroy-Semibold", sans-serif;
}
.step__two,
.step__four {
    padding: 1.5rem 0;
}

@media only screen and (max-width: 768px) {
    .home > .flex {
        flex-direction: column-reverse;
    }
    .right {
        padding: 1rem;
    }
    .right > h1 {
        text-align: center;
    }
    .steps > div {
        padding: 1rem 0;
    }
    .steps h1 {
        margin: 0;
        text-align: center;
    }
    .steps p {
        margin-top: 0;
        /* border: 1px solid red; */
    }
    .steps__CTA {
        margin-top: 1.8rem;
        margin-bottom: 2.5rem;
        width: 100%;
        text-align: center;
    }
    .left {
        padding: 0 1.2rem;
    }
    .left p {
        max-width: 40ch;
    }
}
</style>
