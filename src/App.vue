<template>
  <div class="cont">
      <h1>
        {{ title }}
      </h1>
  </div>
  <Modal />
</template>

<script>
 import Modal from './components/Modal.vue';
export default{
    name: 'App',
    components: { Modal },
    data(){
      return{
        title: 'Modal'
      }
    }
}

</script>

<style scoped>
   .cont{
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 2rem auto;
   }

   h1{
      color: blue;
      font-size: 4rem;
   }
</style>
