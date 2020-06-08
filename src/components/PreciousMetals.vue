<template>
<div class="d-flex justify-content-center">
    <div class="flex-column  mt-5 ">
      <img
        style="mix-blend-mode: multiply;"
        :src="this.$store.getters.website.websitesrc"
        width="400"
        alt="no pic"
      />
      <form class="mt-5" @submit.prevent="submitInfo">
          <v-row align="center">
              <v-col>
                  <v-select
                  v-model="_Curr"
                  :items="CurrItems"
                  menu-props="auto"
                  label="Currency"
                  hide-details
                  prepend-icon="mdi mdi-map"
                  single-line
                  ></v-select>
              </v-col>
          </v-row>
         
      </form>
           <form class="mt-5" @submit.prevent="submitInfo">
          <v-row align="center">
              <v-col>
                  <v-select
                  v-model="_Wgt"
                  :items="Wgtitems"
                  menu-props="auto"
                  label="Weight"
                  hide-details
                  prepend-icon="mdi mdi-map"
                  single-line
                  ></v-select>
              </v-col>
          </v-row>         
        <v-btn
          type="submit"
          class="white--text"
          color="#164e87"
          :loading="loading"
          >Scrape now</v-btn
        >
           </form>
      </div>
    </div>
</template>


<style>
    #metal{
        align-content: center;
    }
    .card{
  width: 60%;
}

</style>

 <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
 <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js" integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous"></script>

<script>
import api from '../api';
export default {
    data(){
        return{
            _Curr:null,
            _Wgt:null,

        CurrItems:[       
"USD",
"AED",
"AFN",
"ALL",
"AMD",
"ANG",
"AOA",
"ARS",
"AUD",
"AWG",
"AZN",
"BAM",
"BBD",
"BDT",
"BGN",
"BHD",
"BIF",
"BMD",
"BND",
"BOB",
"BRL",
"BSD",
"BTN",
"BWP",
"BYN",
"BZD",
"CAD",
"CDF",
"CHF",
"CLP",
"CNY",
"COP",
"CRC",
"CUC",
"CUP",
"CVE",
"CZK",
"DJF",
"DKK",
"DOP",
"DZD",
"EGP",
"ERN",
"ETB",
"EUR",
"FJD",
"FKP",
"GBP",
"GEL",
"GGP",
"GHS",
"GIP",
"GMD",
"GNF",
"GTQ",
"GYD",
"HKD",
"HNL",
"HRK",
"HTG",
"HUF",
"IDR",
"ILS",
"IMP",
"INR",
"IQD",
"IRR",
"ISK",
"JEP",
"JMD",
"JOD",
"JPY",
"KES",
"KGS",
"KHR",
"KMF",
"KPW",
"KRW",
"KWD",
"KYD",
"KZT",
"LAK",
"LBP",
"LKR",
"LRD",
"LSL",
"LYD",
"MAD",
"MDL",
"MGA",
"MKD",
"MMK",
"MNT",
"MOP",
"MRO",
"MUR",
"MVR",
"MWK",
"MXN",
"MYR",
"MZN",
"NAD",
"NGN",
"NIO",
"NOK",
"NPR",
"NZD",
"OMR",
"PAB",
"PEN",
"PGK",
"PHP",
"PKR",
"PLN",
"PYG",
"QAR",
"RON",
"RSD",
"RUB",
"RWF",
"SAR",
"SBD",
"SCR",
"SDG",
"SEK",
"SGD",
"SHP",
"SLL",
"SOS",
"SRD",
"STD",
"SVC",
"SYP",
"SZL",
"THB",
"TJS",
"TMT",
"TND",
"TOP",
"TRY",
"TTD",
"TWD",
"TZS",
"UAH",
"UGX",
"USD",
"UYU",
"UZS",
"VEF",
"VND",
"VUV",
"WST",
"XAF",
"XCD",
"XOF",
"XPF",
"YER",
"ZAR",
"ZMW"
        ]
       , Wgtitems:[
            "g",
            "kg",
            "oz"
        ]
        }
    },
    methods:{
        submitInfo(){
          
            
            api.GoldmetalQuery(this._Curr,this._Wgt);
            api.SilvermetalQuery(this._Curr,this._Wgt);
        }
    }
}
</script>