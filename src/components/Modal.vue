<template>
    <div>
        <div 
            class="backdrop" 
            @click.self="closeBackDrop"
        >
            <div 
                class="modal" 
                :class="{ myTheme : theme === 'feel' }"
            >
                <h1>
                    {{ header }}
                </h1>
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
        },
        methods:{
            closeBackDrop(){
                this.$emit('close');
            }
        }
   }
</script>
