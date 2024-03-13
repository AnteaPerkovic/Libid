<script setup>
import Navigacija from "../components/Navigacija.vue";
import Bottom from "../components/Bottom.vue";
</script>

<template>
    <div
        v-if="spinner"
        class="spinner-border position-absolute top-50 end-50 text-dark"
        role="status"
    >
        <span class="sr-only">Loading...</span>
    </div>

    <div v-else>
        <Navigacija />
        <div class="container">
            <div class="d-flex gap-3 flex-column align-items-center mt-5">
                <h1 class="fs-1">Dobrodošli u našu knjižnicu!</h1>
                <p class="fs-4" style="text-align:center">
                    Otvarajući vrata naše knjižnice otkrijte čaroliju čitanja knjiga koje vam nudimo.
                    Pridružite nam se još danas i uživajte u raličitim pogodnostima.
                </p>
               
            </div>
        </div>
        <div class="d-flex gap-4 flex-column justify-content-center align-items-center mt-5" style="background-color: #EAF3F4; margin-top: 200px !important;">
            <img class="libidImg img-fluid" src="../images/mountains.png" alt="" />
            <h1 class="text-desc">Dobrodošli u knjižnicu gdje riječi postaju avantura!</h1>
            <p class="col-lg-5 col-md-5  col-12 col-sm-8  text-desc">
                Mi smo tu da vam
      pomognemo otkriti čaroliju čitanja, istraživanja novih svjetova i
      stvaranja nezaboravnih iskustava. Naša bogata kolekcija knjiga nudi
      raznolikost žanrova i tema, a naša stručna ekipa stoji vam na raspolaganju
      kako bi vam pomogla pronaći savršenu knjigu za vaše čitateljske užitke.
            </p>
            <button class="btn Btnn text-light p-3"  style=" margin-bottom: 100px !important;">
                <router-link to="/contact"
                                class="nav-link text-dark"
                                
                                >Kontaktirajte nas!</router-link
                            ></button>

        </div>

        <Bottom class="footer" />
    </div>

    <Bottom />

</template>

<script>

import axios from "axios";
export default {
    data() {
        return {
            isLogged: false,
            user: [],
            spinner: false,
        };
    },
    created() {
        this.jelPrijavljen();
    },
    methods: {
        jelPrijavljen() {
            this.spinner = true;
            axios
                .get("/prijavljen")
                .then((response) => {
                    this.user = response.data.user;
                    this.isLogged = true;
                    this.spinner = false;
                    if (this.isLogged == true) {
                        console.log("PRIJAVLJEN JE KORISNIK", this.user);
                    }
                })
                .catch((error) => {
                    console.log(error);
                    this.spinner = false;
                });
        },
    },
};
</script>

<style scoped>
.footer{
  position: relative !important;
}

.Btn {
    background-color: #0096b5;
    border: none;
    border-radius: 20px;
}

.Btnn{
    background-color: #0096b5;
    border: none;
    border-radius: 20px;
    position: relative;
    bottom:100px;
}

.text-desc{
    line-height: 30px;
    letter-spacing: 0.6px;
    position:relative;
    bottom:100px;
}

.libidImg{
    position:relative;
    bottom:17vh;
    overflow: hidden;
}
</style>
