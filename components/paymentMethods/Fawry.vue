<template>
    <v-container fluid>
        <v-row justify="center" class="flex-row-reverse">


            <div class="text-center">
                <v-dialog v-model="alertDialog.show" persistent max-width="500"  >

                    <v-card>
                        <v-card-title style="font-family: Cairo !important; font-weight: bold"
                                      class="headline text-center justify-center">
                            {{alertDialog.title}}
                        </v-card-title>
                        <v-card-text class="text-center">
                            <v-icon class="d-block overflow-hidden" size="100"
                                    :color="`${alertDialog.error ?'red' : 'green'}`">
                                {{alertDialog.error ? 'mdi-minus-circle': 'mdi-check-circle' }}
                            </v-icon>
                            <h1 style="color: black !important; font-family: Cairo !important; font-weight: bold"
                                v-html="alertDialog.text"></h1>


                        </v-card-text>
                        <v-card-actions class="text-center justify-center">
                            <v-btn color="white darken-1" :class="`${alertDialog.error ?'red' : 'green'}`" text
                                   @click="alertDialog.show =false">
                                Ok
                            </v-btn>

                        </v-card-actions>
                    </v-card>
                </v-dialog>
                <v-dialog
                        v-model="loading" persistent width="300">
                    <v-card class="text-center justify-center">
                        <v-card-title class="text-center justify-center">
                            <div id="head" style="color:black" class=" text-h5">جاري تنفيذ طلبك</div>
                        </v-card-title>
                        <v-card-text class="row justify-center text-center">
                            <SemipolarSpinner :animation-duration="1500" :size="100" color="indigo"/>
                        </v-card-text>
                    </v-card>
                </v-dialog>
            </div>
            <div class="text-center">
                <v-dialog
                        v-model="loading" persistent width="300">
                    <v-card class="text-center justify-center">
                        <v-card-title class="text-center justify-center">
                            <div id="head" style="color:black" class=" text-h5">جاري تنفيذ طلبك</div>
                        </v-card-title>
                        <v-card-text class="row justify-center text-center">
                            <SemipolarSpinner :animation-duration="1500" :size="100" color="indigo"/>
                        </v-card-text>
                    </v-card>
                </v-dialog>
            </div>
            <v-col xs="12" md="3" sm="12">
                <v-card class="h-100" outlined elevation="10">
                    <v-img contain max-height="250" :aspect-ratio="16/9"
                           :src="require('~/assets/images/payment/Fawry payment banner.png')"></v-img>
                    <v-card-text class="pa-0 mx-0 flex-grow-1 text-center  font-weight-bold">
                        <p class="mx-2 text-left px-4">
                            After the free trial expires,
                            Stickyposts will deduct the subscription amount from your mobile balance. Free trial is for
                            new
                            subscribers
                            if you are an Orange Customers send end “Unsub Sticky” to 5030 ,
                            For Vodafone Customers Send “Unsub Sticky” to 6699 ,For We Customers Send “Unsub Sticky” to
                            4041 and For
                            Etisalat Customers Send “Unsub Sticky” to 1722 Or visit our website to cancel
                            subscription.</p>
                    </v-card-text>
                </v-card>
            </v-col>
            <v-col xs="12" md="4" sm="12">
                <v-card outlined elevation="10" height="400">
                    <v-card-title class="justify-center">
                        <h2 class="py-4">GET <span style="color:red;font-size:35px;font-weight:bold"> 30% </span> OFF
                        </h2>
                    </v-card-title>

                    <v-card-text class="text-center">
                        <p for="rpwd" class="text-center fs-16 mb-20">Enter Promocode ( <span
                                style="font-weight:bold; font-size:22px; color:#320b82;"> JKJAKATM </span> ) to get 30%
                            off on all our
                            package</p>


                        <v-row class="justify-center">
                            <v-col class="mx-0 px-0" sm="12" md="6" xl="4">
                                <v-text-field dense outlined label="Promo Code" color="success"></v-text-field>
                            </v-col>

                            <v-col sm="12" md="6" xl="4" class="mx-2 px-0 text-center ">
                                <v-btn append color="success">
                                    <v-icon left>
                                        mdi-check-circle
                                    </v-icon>
                                    Active
                                </v-btn>
                            </v-col>
                        </v-row>

                        <div class="text-center ">


                            <v-btn @click="greet" x-large class="mx-10 yellow accent-4 font-weight-bold text--accent-4">
                                Subscribe
                                <v-icon tag="span" class="mx-2">
                                    mdi-cash-usd

                                </v-icon>
                            </v-btn>
                        </div>
                    </v-card-text>


                </v-card>
            </v-col>
            <v-col xs="12" md="3" sm="12">
                <v-card class="h-100" elevation="10" outlined>
                    <div class="d-flex justify-space-around align-center pt-4 m-0 purple darken-4">
                        <v-img class="ma-1" contain height="23" max-width="70" width="70"
                               :src="require('~/assets/images/payment/visaandmastercard.png')"></v-img>
                        <p class="text-center font-weight-bold white--text text-lg-h4">Pay by Credit Card</p>
                    </div>
                    <v-card-text class="text-center mx-0 px-0">
                        <div>
                            <ul class="text-left font-weight-bold payment-ul pl-6 pr-3">
                                <li>Insert any available promo code to get discount</li>
                                <li>Insert your correct Email Address</li>
                                <li>Insert your correct phone number</li>
                                <li>Receive your activation code</li>
                                <li>Pay in the nearest Fawry from your location</li>
                            </ul>
                        </div>
                    </v-card-text>
                </v-card>
            </v-col>
            <!--  </v-card>-->
        </v-row>
    </v-container>
</template>
<style>
    .payment-ul li {
        padding: 5px 0;
    }

    .h-100 {
        height: 100%;
    }
</style>
<script>
    import {SemipolarSpinner} from 'epic-spinners'

    export default {
        components: {
            SemipolarSpinner
        },
        name: "Fawry",
        data() {
            return {

                loading: false,
                alertDialog: {
                    show: false,
                    error: false,
                    title: 'Dialog',
                    text: 'Text'
                },


                users: ['asdasd', 'asd']
            }
        },
        methods: {
            showalert: function ($options) {
                this.alertDialog = $options;
            },

            greet: function () {


              console.log('asdasd');
                // let vm = this;

                // this.loading = true;
                // this.postdata = {
                //     "customerName": "shawky",
                //     "customerMobile": "01061520610",
                //     "customerEmail": "shawky@gmail.com",
                //     "amount": "500.00",
                //     "chargeItems": [
                //         {
                //             "itemId": "12",
                //             "description": "salary",
                //             "price": "500.00",
                //             "quantity": "1"
                //         }
                //     ]
                // }
                //
                // this.axios.post('https://crmmrkt.com/MediaGateAPI/payment/FawryPay/charge', this.postdata)
                //     .then(function (response) {
                //         vm.loading = false;
                //         vm.showalert({
                //             'show': true,
                //             'error': false,
                //             'title': 'Done',
                //             'text': "Here's Your Refrence Number <br>" + '<b style="font-size: 4rem;">' + response.data.referenceNumber + '</b>'
                //         })
                //         console.log(response);
                //     })
                //     .catch(function (error) {
                //         vm.loading = false;
                //         console.log(error);
                //         vm.showalert({
                //             'show': true,
                //             'error': true,
                //             'title': 'خطأ',
                //             'text': "خطأ بالدفع يرجي المحاولة مرة اخري"
                //         })
                //     })
                //     .then(function () {
                //         vm.loading = false;
                //     });
            },
        },
        mounted() {


        },
        created() {

        }

    }


</script>

<style scoped>

</style>
