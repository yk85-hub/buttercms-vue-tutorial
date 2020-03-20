<template>
  <v-row align="center">
    <v-col class="text-center" cols="12" sm="4">
      <div class="my-2">
        <v-btn text small>Normal</v-btn>
      </div>
      <div class="my-2">
        <v-btn text small color="primary">Primary</v-btn>
      </div>
      <div class="my-2">
        <v-btn text small color="error">Error</v-btn>
      </div>
      <div class="my-2">
        <v-btn text small disabled>Disabled</v-btn>
      </div>
    </v-col>

    <v-col class="text-center" cols="12" sm="4">
      <div class="my-2">
        <v-btn text>Normal</v-btn>
      </div>
      <div class="my-2">
        <v-btn text color="primary">Primary</v-btn>
      </div>
      <div class="my-2">
        <v-btn text color="error">Error</v-btn>
      </div>
      <div class="my-2">
        <v-btn text disabled>Disabled</v-btn>
      </div>
    </v-col>

    <v-col class="text-center" cols="12" sm="4">
      <div class="my-2">
        <v-btn text large>Normal</v-btn>
      </div>
      <div class="my-2">
        <v-btn text large color="primary">Primary</v-btn>
      </div>
      <div class="my-2">
        <v-btn text large color="error">Error</v-btn>
      </div>
      <div class="my-2">
        <v-btn text large disabled>Disabled</v-btn>
      </div>
    </v-col>
  </v-row>
</template>


<script>
  import { butter } from '@/buttercms'
  export default {
    name: 'customer-page',
    data() {
      return {
        slug: this.$route.params.slug,
        page: {
          slug: '',
          fields: {}
        }
      }
    },
    methods: {
      getPage() {
        butter.page.retrieve('customer_case_study', this.slug)
          .then((res) => {
            console.log(res.data.data)
            this.page = res.data.data
          }).catch((res) => {
            console.log(res)
          })
      }
    },
    created() {
      this.getPage()
    }
  }
</script>

<style>
  
</style>
