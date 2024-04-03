<template>
  <div class="cont">
      <h1>
        {{ title }}
      </h1>
  </div>
    <Modal 
      :header="header" 
      :text="text" 
      :theme="theme" 
    />
</template>

<script>
 import Modal from './components/Modal.vue';
export default{
    name: 'App',
    components: { Modal },
    data(){
      return{
        title: 'Modal',
        header: 'give away for everyone',
        text: 'grab yours now!',
        theme: 'feel'
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

<!-- 

   MODAL PROJECT

   what we'll learn in this project are:

   1. how to build  a modal component with Vuejs, using the vue;
   2 how to build backdrop and customize your modal theme using the theme as props that's passed from parent components
   3. how to use props to send data from parent to child component
   4. how to use props in different ways at beginners level
   5.dynamic way of using props
   6. how to use scoped and global scoped


   => data() : in a simple term data() is a function that returns an object, all vue properties are declare inside data before they can be use anywhere in your component
   => methods function in vue is use to store all functions in vue instance
   => props is a method used to send data from parent to child components

 -->
