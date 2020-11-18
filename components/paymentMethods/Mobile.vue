<template>
  <v-container fluid>
    <v-row justify="center" class="flex-row-reverse">

      <v-col xs="12" md="3" sm="12">
        <v-card outlined elevation="10">

          <v-img contain max-height="250" :aspect-ratio="16/9"
                 :src="require('../../assets/images/payment/Mobile payment banner.png')"></v-img>
          <v-card-text class="pa-0 mx-0 flex-grow-1 text-center">
            <p class="mx-2">You will lose the remaining subscription from the current plan
              You must check the balance to subscribe to the new package</p>

          </v-card-text>


        </v-card>
      </v-col>


      <v-col xs="12" md="4" sm="12">
        <v-card outlined elevation="10" height="400">

          <v-card-text class="text-center">
            <v-text-field dense outlined label="Phone Number" color="success"></v-text-field>
            <v-text-field dense type="email" outlined label="E-Mail" color="success"></v-text-field>
            <v-select

                item-text="text"
                item-value="value"
                :items="operators_select"
                label="Mobile Network"
                dense
            ></v-select>
            <p for="rpwd" class="text-center fs-16 mb-20">Enter Promocode ( <span
                style="font-weight:bold; font-size:22px; color:#320b82;"> JKJAKATM </span> ) to get 30% off on all our
              package</p>

            <v-text-field dense outlined label="Promo Code" color="success"></v-text-field>

            <v-row class="justify-center">

              <v-btn min-width="50" x-large class="mx-10 primary">
                Subscribe
              </v-btn>


            </v-row>

          </v-card-text>


        </v-card>
      </v-col>

      <v-col xs="12" md="3" sm="12">
        <v-card elevation="10" outlined>
          <div class="d-flex justify-space-around align-center pt-4 m-0 purple darken-4">
            <v-img class="ma-1" contain height="70" max-width="50" width="50"
                   :src="require('../../assets/images/payment/mob.png')"></v-img>
            <p class="text-center font-weight-bold white--text text-lg-h4">Pay by Mobile</p>

          </div>


          <v-card-text class="text-center mx-0 px-0">
            <div>
              <ul class="text-left">
                <li>Choose pay by mobile from the available options</li>
                <li>Insert your correct phone number</li>
                <li>Insert any available promo code to get discount</li>
                <li>Receive the activation SMS</li>
                <li>Insert the activation code</li>
                <li>Press subscribe to complete the process</li>
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
  name: "Mobile",
  data: () => ({

    operators_select: [
      {value: 'STC_BHR', text: 'STC - BHR'},
      {value: 'Batelco_BHR', text: 'Batelco - BHR'},
      {value: 'Orange_EGY', text: 'Orange - EGY'},
      {value: 'Vodafone_EGY', text: 'Vodafone - EGY'},
      {value: 'Etisalat_EGY', text: 'Etisalat - EGY'},
      {value: 'WE_EGY', text: 'WE - EGY'},
      {value: 'Umniah_JOR', text: 'Umniah - JOR'},
      {value: 'Telkom_KEN', text: 'Telkom - KEN'},
      {value: 'STC_KWT', text: 'STC - KWT'},
      {value: 'Ooredoo_KWT', text: 'Ooredoo - KWT'},
      {value: 'Libyana_LBY', text: 'Libyana - LBY'},
      {value: 'Ooredoo_OMN', text: 'Ooredoo - OMN'},
      {value: 'Jawwal_PSE', text: 'Jawwal - PSE'},
      {value: 'Ooredoo_PSE', text: 'Ooredoo - PSE'},
      {value: 'Ooredoo_QAT', text: 'Ooredoo - QAT'},
      {value: 'Vodafone_QAT', text: 'Vodafone - QAT'},
      {value: 'Zain_SAU', text: 'Zain - SAU'},
      {value: 'Orange_TUN', text: 'Orange - TUN'},
      {value: 'Du_ARE', text: 'Du - ARE'},
      {value: 'Etisalat_ARE', text: 'Etisalat - ARE'},
      {value: 'Zain_KWT', text: 'Zain - KWT'},
      {value: 'Orange_JOR', text: 'Orange - JOR'},
      {value: 'Zain_JOR', text: 'Zain - JOR'},
      {value: 'Zain_BHR', text: 'Zain - BHR'},
      {value: 'Ooredoo_ALG', text: 'Ooredoo - ALG'},
      {value: 'Dialog_SRI', text: 'Dialog - SRI Lanka'},


    ]

  }),
}

</script>

<style scoped>

</style>

