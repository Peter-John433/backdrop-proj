<template>
  <div class="cont">
      <h1>
        {{ title }}
      </h1>
  </div>
  <!-- <div v-if="showModal">
     <Modal 
        :header="header" 
        :text="text" 
        :theme="theme" 
        @close="closeBack"
      />
  </div> -->
    <Teleport to="#modal-el">
      <div v-if="showModal">
        <ModalSlot theme="feel" @close="toggleModal">
            <h1>give away for everyone</h1>
            <p>grab yours now!</p>

          <template v-slot:links>
            <div>
              <a href="#">SignUp</a>
              <a href="#">SignIn</a>
            </div>
          </template>
        </ModalSlot>
      </div>
    </Teleport>

    <!-- reusing component -->
    <Teleport to=".modal-class">
      <div v-if="showModal2" class="modal2">
        <ModalSlot @close="toggleModal2">
            <h1>great opportunity</h1>
            <p>grab yours now!</p>
        </ModalSlot>
      </div>
    </Teleport>
   <!-- closed -->
    <div class="welcome">
        welcome...
    </div>

    <div class="btn">
      <button @click="toggleModal">show modal1</button>
      <button @click="toggleModal2">show modal2</button>
    </div>
</template>

<script>
//  import Modal from './components/Modal.vue';
 import ModalSlot from './components/ModalSlot.vue';
export default{
    name: 'App',
    // components: { Modal },
    components: { ModalSlot },
    data(){
      return{
        title: 'Modal',
        // header: 'give away for everyone',
        // text: 'grab yours now!',
        // theme: 'feel',
        showModal: false,
        showModal2: false
      }
    },

    methods:{
       toggleModal(){
         this.showModal = !this.showModal;
       },
       toggleModal2(){
          this.showModal2 = !this.showModal2;
       }
    }
}

</script>

<style scoped>
   .btn{
     display: flex;
     justify-content: center;
     gap: 1rem;
     margin-top: 1rem;
   }
   button{
      background-color: green;
      color: white;
      border: 1px solid white;
      outline: 2px solid green;
      display: block;
      text-align: center;
      
      padding: 10px 16px;
      cursor: pointer;
   }

   .modal2 h1{
      margin-top: 2rem;
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

   Props

   props pass data from parent straight into the child component
   -data pass can be of any of the datatypes 
   -props cand be sent as one time or two way  binding 
   
   note: to make your code look more cleaner and professional, we should always bind our props to variables declear in the data instance.
   props is always use here to change the theme of the modal and make it look more customizable 

   EVENTS

   ==> events in vue  are like callbacks that you can listen for when something happens on an element. events  are triggered by elements and they can trigger anything from a function declared in the script or in an expression delcared in inline handler.
     events help us interact with our website effectively,here we'll be looking at few things about events
     this things includes:
     i. types of events
     ii. events directives
     iii. emit() function
     iv. custom event
     v. event modifiers
     vi. slot
     vii. teleport


     ==> types of events includes:
      i inline handler
      ii. methods handler

      ==> events directive is use to make something happen when an event occurs on an element. i.e the v-on directive which can also be short handed to @

      ==> emit function $emit() = is use to pass custom event to a parent comparent.
       
      VUE SLOTS
      ==> slot is a placeholder that is use to pass content from parent to a child component, slot do not need registration or configuration like props.
      ==> slot without a name is scalled a default slot 
      ==> slot with a name is called a name slot 
      ==> name slot is use to move the content from the parent component into a particular part in a child component, or it use to direct the location of a content in child component, furthermore name slot are use on components or templates, i.e a template can be define inside a component for a name slot to be render inside while content outside the name slot are regard as default slot.

      note: when a component as no content in it't template tag  then that will be treated as a default slot.
      
      VUE TELEPORT

      ==> teleport are use to send some element from one part of app to another part  of the application. teleport allow you to take a full contents from a vue app and render it outside the app with all styles and scripts intact.
      teleport is very easy and simple to learn.
      
 -->
