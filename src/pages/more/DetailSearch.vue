<template>
  <div style="min-height:100%">
    <v-toolbar tabs fixed color="white">
      <v-btn icon @click.native="history.back()">
            <v-icon>arrow_back</v-icon>
      </v-btn>
      <v-toolbar-title>Pencarian Detail</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>refresh</v-icon>
      </v-btn>
    </v-toolbar>
    <v-layout row>
      <v-flex xs12 sm6 offset-sm3 class="pa-4">
        <v-form v-model="valid" ref="form" lazy-validation>
          
          <v-btn class="mt-4" dark block @click.native="console.log('Submited')" color="orange darken-3" :disabled="!valid">Lihat Hasil</v-btn>
        </v-form>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
  export default {
    data: () => ({
      e1: true,
      valid: true,
      form: {
        price: { label: 'Harga Properti (Rupiah)', value: 500000000, hide: true },
        dp: { label: 'Jumlah Uang Muka (DP)', value: 100000000, hide: true },
        dpPercentage: { label: 'DP (%)', value: 20.0, hide: true },
        fixedInterestDuration: { label: 'Durasi Bunga Fixed (Tahun)', value: 3, hide: true },
        fixedInterest: { label: 'Bunga Fixed (%)', value: 9.5, hide: true },
        floatInterest: { label: 'Bunga Float (%)', value: 11, hide: true },
        installmentDuration: { label: 'Lama Angsuran (Tahun)', value: 15, hide: true }
      },
      select: null
    }),
    methods: {
      submit () {
        if (this.$refs.form.validate()) {
          // Native form submission is not yet supported
        }
      },
      clear () {
        this.$refs.form.reset()
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
