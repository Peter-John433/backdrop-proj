<template>
    <div>
        <div class="backdrop">
            <div class="modal" :class="{ myTheme : theme === 'feel' }">
                <h1>{{ header }}</h1>
                <p>
                    {{ text }}
                </p>
                <!-- <div>
                    <textarea name="" id="" cols="30" rows="10"></textarea>
                </div> -->
            </div>
        </div>
    </div>
</template>

<script>
   export default{
        props:['header', 'text', 'theme'],
        data(){
            return{
                modalTitle: 'Modal'
            }
        }
   }
</script>

<style scoped>
  .backdrop{
    position: fixed;
    top: 0%;
    background-color: rgba(0, 0, 0, .5);
    width: 100%;
    height: 100%;
  }

  .modal{
     display: flex;
     flex-direction: column;
     justify-content: start;
     align-items: center;
     /* height: 100%; */
     margin: 5rem auto;
     width: 500px;
     background-color: white;
     padding: 10px;
     border-radius: 16px;
     height: 200px;
  }

  .modal h1{
     color: blue;
     font-size: 2rem;
     text-transform: capitalize;
     text-decoration: underline;
  }

  .modal p{
     margin-top: 2rem;
     text-transform: capitalize;
     font-weight: bold;
  }

  textarea{
     width: 400px;
     margin-top: 1rem;
     border-radius: 16px;
     resize: none;
  }

  .myTheme{
      background-color: red;
      color: white;
   }
.myTheme h1{
    color: white;
}
</style>
