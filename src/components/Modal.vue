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
            </div>
        </div>
    </div>
</template>

<script>
   export default{
        props:['header', 'text', 'theme'],
        methods:{
            closeBackDrop(){
                this.$emit('close');
            }
        }
   }
</script>
