<template>
  <v-container>
    <v-row class="mx-auto text-center justify-center">
      <div id="head" class="col-12 col-md-12 col-sm-12 transition-swing text-h1">الصراف</div>
      <div id="head" class="col-12 col-md-12 col-sm-12 transition-swing text-h4 font-weight-light"> وسيلة دفعك الأولي
      </div>
      <v-col class="col-xl-10 col-md-12 col-sm-10" style="z-index: 17 !important;">
        <v-responsive aspect-ratio="9/16">
          <v-card elevation="10">
            <v-card-text>
              <v-tabs color="purple" grow icons-and-text centered v-model="tab" align-with-title>
                <v-tab>
                  <v-img contain class="container--fluid black " :aspect-ratio="16/9" width="186"
                         height="41" :src="require('../assets/images/payment/apple.svg')"></v-img>
                </v-tab>
                <v-tab>
                  <v-img contain class="container--fluid" :aspect-ratio="16/9" width="186" height="41"
                         :src="require('../assets/images/payment/google..svg')"></v-img>
                </v-tab>
                <v-tab>
                  <v-img contain class="container--fluid" :aspect-ratio="16/9" width="186" height="41"
                         :src="require('../assets/images/payment/meeza.png')"></v-img>
                </v-tab>
                <v-tab>
                  <v-img contain class="container--fluid" :aspect-ratio="16/9" width="186" height="41"
                         :src="require('../assets/images/payment/fawry-pay-english-logo-11111.png')"></v-img>
                </v-tab>
                <v-tab>
                  <v-img contain class="container--fluid" :aspect-ratio="16/9" width="186" height="41"
                         :src="require('../assets/images/payment/visaandmastercard.png')"></v-img>
                </v-tab>
                <v-tab>
                  <v-img contain class="container--fluid" :aspect-ratio="16/9" width="186" height="41"
                         :src="require('../assets/images/payment/mob.png')"></v-img>
                </v-tab>

              </v-tabs>
              <v-tabs-items v-model="tab">
                <v-tab-item>


                  <apple-pay></apple-pay>


                </v-tab-item>

                <v-tab-item>
                  <GooglePay></GooglePay>

                </v-tab-item>


                <v-tab-item>
                  <meeza></meeza>

                </v-tab-item>


                <v-tab-item>
                  <PayPal></PayPal>

                </v-tab-item>

                <v-tab-item>

                  <credit-card></credit-card>

                </v-tab-item>

                <v-tab-item>
                  <mobile></mobile>
                </v-tab-item>


              </v-tabs-items>


            </v-card-text>

            <v-card-actions>

              <v-btn class="primary" @click="say()" prepend-icon="mdi-account-circle">Pay</v-btn>

            </v-card-actions>

          </v-card>
        </v-responsive>
      </v-col>


    </v-row>

  </v-container>
</template>

<script>
import ApplePay from "@/components/paymentMethods/ApplePay";
import CreditCard from "@/components/paymentMethods/CreditCard";
import Mobile from "@/components/paymentMethods/Mobile";
import GooglePay from "@/components/paymentMethods/GooglePay";
import Meeza from "@/components/paymentMethods/Meeza";
import PayPal from "@/components/paymentMethods/PayPal";
import Fawry from "@/components/paymentMethods/Fawry";


export default {
  name: 'PaymentModule',
  components: {Fawry, Meeza, PayPal, GooglePay, Mobile, CreditCard, ApplePay},
  data: () => ({
    tab: 5,
    width: 300,
    height: 300,


  }),
  methods: {
    say: function () {

    }
  }
  ,
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700&display=swap');

#head {
  font-family: Cairo !important;
  font-weight: bold;
  color: white;
}


@import url('https://fonts.googleapis.com/css?family=Exo:400,700');

* {
  margin: 0px;
  padding: 0px;
  line-height: 1.2;
}


.context {
  width: 100%;
  position: absolute;
  top: 50vh;

}

.context h1 {
  text-align: center;
  color: #fff;
  font-size: 50px;
}


.area {
  background: #4e54c8;
  background: -webkit-linear-gradient(to left, #8f94fb, #4e54c8);
  width: 100%;
  height: 100vh;


}

.circles {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.circles li {
  position: absolute;
  display: block;
  list-style: none;
  width: 20px;
  height: 20px;
  background: rgba(255, 255, 255, 0.2);
  animation: animate 5s linear infinite;
  bottom: -150px;

}

.circles li:nth-child(1) {
  left: 25%;
  width: 80px;
  height: 80px;
  animation-delay: 0s;
}


.circles li:nth-child(2) {
  left: 10%;
  width: 20px;
  height: 20px;
  animation-delay: 2s;
  animation-duration: 12s;
}

.circles li:nth-child(3) {
  left: 70%;
  width: 20px;
  height: 20px;
  animation-delay: 4s;
}

.circles li:nth-child(4) {
  left: 40%;
  width: 60px;
  height: 60px;
  animation-delay: 0s;
  animation-duration: 18s;
}

.circles li:nth-child(5) {
  left: 65%;
  width: 20px;
  height: 20px;
  animation-delay: 0s;
}

.circles li:nth-child(6) {
  left: 75%;
  width: 110px;
  height: 110px;
  animation-delay: 3s;
}

.circles li:nth-child(7) {
  left: 35%;
  width: 150px;
  height: 150px;
  animation-delay: 7s;
}

.circles li:nth-child(8) {
  left: 50%;
  width: 25px;
  height: 25px;
  animation-delay: 15s;
  animation-duration: 30s;
}

.circles li:nth-child(9) {
  left: 20%;
  width: 15px;
  height: 15px;
  animation-delay: 2s;
  animation-duration: 15s;
}

.circles li:nth-child(10) {
  left: 85%;
  width: 150px;
  height: 150px;
  animation-delay: 0s;
  animation-duration: 5s;
}


@keyframes animate {

  0% {
    transform: translateY(0) rotate(0deg);
    opacity: 5;
    border-radius: 0;
  }

  100% {
    transform: translateY(-1000px) rotate(720deg);
    opacity: 0;
    border-radius: 50%;
  }

}

@keyframes move_wave {
  0% {
    transform: translateX(0) translateZ(0) scaleY(1)
  }
  50% {
    transform: translateX(-25%) translateZ(0) scaleY(0.55)
  }
  100% {
    transform: translateX(-50%) translateZ(0) scaleY(1)
  }
}

.waveWrapper {

  margin: auto;
  z-index: 0 !important;
}

.waveWrapperInner {
  position: fixed;
  width: 100%;
  overflow: hidden;
  height: 100%;
  bottom: 0;
}

.bgTop {
  z-index: 15;
  opacity: 0.5;
}

.bgMiddle {
  z-index: 10;
  opacity: 0.75;
}

.bgBottom {
  z-index: 5;
}

.wave {
  position: absolute;
  left: 0;
  width: 200%;
  height: 100%;
  background-repeat: repeat no-repeat;
  background-position: 0 bottom;
  transform-origin: center bottom;
}

.waveTop {
  background-size: 50% 100px;
}

.waveAnimation .waveTop {
  animation: move-wave 3s;
  -webkit-animation: move-wave 3s;
  -webkit-animation-delay: 1s;
  animation-delay: 1s;
}

.waveMiddle {
  background-size: 50% 120px;
}

.waveAnimation .waveMiddle {
  animation: move_wave 10s linear infinite;
}

.waveBottom {
  background-size: 50% 100px;
}

.waveAnimation .waveBottom {
  animation: move_wave 15s linear infinite;
}
</style>
