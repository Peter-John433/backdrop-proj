<template>
    <div>
        <div class="backdrop">
            <div class="modal">
                <h1>{{ modalTitle }}</h1>
                <div>
                    <textarea name="" id="" cols="30" rows="10"></textarea>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
   export default{
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
     justify-content: center;
     align-items: center;
     /* height: 100%; */
     margin-top: 5rem;
  }

  .modal h1{
     color: white;
     font-size: 2.7rem;
     text-transform: capitalize;
  }

  textarea{
     width: 400px;
     margin-top: 1rem;
     border-radius: 16px;
     resize: none;
  }
</style>
