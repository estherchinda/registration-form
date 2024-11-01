<template>
  <Nav />
  <MainPage />
  <Modal/>
  <Footer />
</template>

<script>
import Nav from './components/Nav.vue'
import MainPage from './components/MainPage.vue'
import Footer from './components/Footer.vue'
import Modal from './components/Modal.vue'



export default {
  name: 'App',
  components: {
   MainPage,
   Nav,
   Footer,
   Modal
  },
  data() {
    return {
      title: 'My first vue app',
      showModal: false,
    }
  }
}
</script>
