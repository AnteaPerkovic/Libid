<script setup>
import Navigacija from "../components/Navigacija.vue";
import Bottom from "../components/Bottom.vue";
</script>

<template>
    <Navigacija />
    <div class="contact">
        <h1 class="text-center mt-5">Kontaktiraj nas</h1>
        <p class="text-center mt-3">
            Imate pitanja? Kontaktirajte nas putem e-maila ili putem tel. broja.
        </p>
        <div
            class="login-form d-flex flex-column justify-content-center align-items-center mt-5"
        >
            <form
                class="bg-light p-5 col-12 col-lg-4 col-md-10 col-sm-10 shadow-lg"
            >
                <div
                    class="head-items d-flex gap-2 justify-content-center align-items-center mb-3"
                >
                    <img
                        src="../images/logo.png"
                        alt=""
                        height="30px"
                        width="auto"
                    />
                    <h3>Kontakt</h3>
                </div>

              <br>

               
                <li>
                    <ul>
                        <h4>Adresa: </h4>
                        
                    </ul>
                    <ul>
                        Libid HNŽ/K
88000 Mostar 
Bosna i Hercegovina
                    </ul>
                </li> 
                

                <li>
                    <ul>
                        <h4>E-mail:</h4>
                        
                    </ul>
                    <ul>
                        ibid.info@gmail.com
                    </ul>
                </li> 

                <li>
                    <ul>
                        <h4> Broj telefona:</h4>
                       
                    </ul>
                    <ul>
                        +387 63 000 000
                    </ul>
                </li> 
              
               
            </form>
        </div>
    </div>
    <Bottom />
</template>

<script></script>

<style scoped>
.contact {
    background-image: url("../images/mountains.png");

    background-size: cover;
    background-repeat: no-repeat;
    height: 900px;
}

.regBtn {
    background-color: #0096b5;
    border: none;
}
</style>
