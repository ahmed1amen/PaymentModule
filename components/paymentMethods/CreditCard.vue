<template>
  <v-container fluid>
    <v-row justify="center" class="flex-row-reverse">

      <v-col xs="12" md="3" sm="12">
        <v-card outlined elevation="10">

          <v-img contain max-height="250" :aspect-ratio="16/9" :src="require('../../assets/images/payment/Visa payment banner.png')"></v-img>
          <v-card-text class="pa-0 mx-0 flex-grow-1 text-center">
            <p class="mx-2">You will lose the remaining subscription from the current plan
              You must check the balance to subscribe to the new package</p>

          </v-card-text>


        </v-card>
      </v-col>


      <v-col xs="12" md="4" sm="12">
        <v-card outlined elevation="10" height="400">
          <v-card-title class="justify-center">
            <h2 class="py-4">GET <span style="color:red;font-size:35px;font-weight:bold"> 30% </span> OFF </h2>
          </v-card-title>

          <v-card-text class="text-center">
            <p for="rpwd" class="text-center fs-16 mb-20">Enter Promocode ( <span
                style="font-weight:bold; font-size:22px; color:#320b82;"> JKJAKATM </span> ) to get 30% off on all our
              package</p>


            <v-row class="justify-center">
              <v-col class="mx-0 px-0"  sm="12" md="6" xl="4">
                <v-text-field dense  outlined label="Promo Code" color="success"></v-text-field>
              </v-col>

              <v-col  sm="12" md="6" xl="4" class="mx-2 px-0 text-center ">
                <v-btn append color="success">
                  <v-icon left>
                    mdi-check-circle
                  </v-icon>
                  Active
                </v-btn>
              </v-col>
            </v-row>

            <div class="text-center">
              <v-btn @click="redirectToCheckout" min-width="50" x-large class="mx-10 primary">
                Subscribe
              </v-btn>
            </div>
          </v-card-text>




        </v-card>
      </v-col>

      <v-col xs="12" md="3" sm="12">
        <v-card elevation="10" outlined>
          <div class="d-flex justify-space-around align-center pt-4 m-0 purple darken-4">
          <v-img class="ma-1" contain height="23" max-width="70" width="70" :src="require('../../assets/images/payment/visaandmastercard.png')"></v-img>
            <p class="text-center font-weight-bold white--text text-lg-h4">Pay by Credit Card</p>

      </div>



          <v-card-text class="text-center mx-0 px-0">
       <div>
         <ul class="text-left">
           <li>Insert any available promo code to get discount</li>
           <li>Insert your card number &amp; the expiry date</li>
           <li>Insert the Cardholder name</li>
           <li>Insert the security code</li>
           <li>Confirm the payment </li>
         </ul>

       </div>
          </v-card-text>


        </v-card>
      </v-col>


      <!--  </v-card>-->
    </v-row>
  </v-container>
</template>

<script>
export default {
  props: {

    cannceld: Function,

  },
  name: "CreditCard",
  mounted() {
    let e = document.createElement('script');
    e.src = `https://banquemisr.gateway.mastercard.com/checkout/version/57/checkout.js`;
    e.type='text/javascript';
    document.getElementsByTagName('head')[0].appendChild(e);
  },
  methods:{
    redirectToCheckout () {
     window.Checkout.configure({
       session: {
         id: '2222222222222222'
       },
       interaction: {
         merchant: {
           name: 'MediaGate',
           address: {
             line1: '200 Sample St',
             line2: '1234 Example Town'
           }
         }
       }
     });

      window.Checkout.showLightbox();
  }

}
}
</script>

<style scoped>

</style>
