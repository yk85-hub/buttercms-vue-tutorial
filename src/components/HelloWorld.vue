<template>
  <div class="hello">
  
  
  
  	<div class="section">
      <div class="container">
        <div class="columns">
          <div class="column has-text-centered">
         Hi, it is my first Vue web app
         
     
         
          </div>
        </div>
      </div>
    </div>
	
  <div class="section">
      <div class="container">
        <div class="columns">
          <div class="column has-text-centered">
  <template>
  <VueSlickCarousel :arrows="true" :dots="true">
    <div><h3>1</h3></div>
    /*...*/
  </VueSlickCarousel>
</template>
  
  <script>
  import 'vue-slick-carousel/dist/slick.css'
  import 'vue-slick-carousel/dist/slick-theme.css'

  import VueSlickCarousel from 'vue-slick-carousel'

  export default {
    name: 'MyComponent',
    components: { VueSlickCarousel },
  }
</script>
  
  
  
  
         </div>
        </div>
      </div>
    </div>
  
    <div class="section">
      <div class="container">
        <div class="columns">
          <div class="column has-text-centered">
            <a href="https://vuejs.org/">
              <figure>
                <img src="../assets/logo.png" alt="Vue logo">
              </figure>
            </a>
          </div>
          <div class="column has-text-centered">
            <a href="https://buttercms.com/">
              <figure>
                <img src="../assets/buttercms.jpg" alt="ButterCMS logo">
              </figure>
            </a>
          </div>
          
          <div class="column has-text-centered">
            <a href="https://buttercms.com/">
              <figure>
                <img src="../assets/buttercms.jpg" alt="ButterCMS logo">
              </figure>
            </a>
          </div>
          
          <div class="column has-text-centered">
            <a href="https://buttercms.com/">
              <figure>
                <img src="../assets/buttercms.jpg" alt="ButterCMS logo">
              </figure>
            </a>
          </div>
          <div class="column has-text-centered">
            <a href="https://buttercms.com/">
              <figure>
                <img src="../assets/buttercms.jpg" alt="ButterCMS logo">
              </figure>
            </a>
          </div>
          
        </div>
      </div>
    </div>
	
	
	

	
	
	
  </div>
</template>

<script>
  import {
    butter
  } from '@/buttercms'
  export default {
    name: 'HelloWorld',
    data() {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    },
    methods: {
      fetchHeadline() {
        butter.content.retrieve(['homepage_headline'])
          .then((res) => {
            console.log('Headline from ButterCMS')
            console.log(res)
          })
      },
      fetchPosts() {
        butter.post.list({
            page: 1,
            page_size: 10
          })
          .then((res) => {
            console.log('Content from ButterCMS')
            console.log(res)
          })
      }
    },
    created() {
      this.fetchHeadline()
      this.fetchPosts()
    }
  }
</script>

<style>
 figure {
    width:;
}
</style>
