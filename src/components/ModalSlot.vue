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
                <slot></slot>
                <div class="links">
                    <slot name="links"></slot>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
   export default{
        props:['theme'],
        methods:{
            closeBackDrop(){
                this.$emit('close');
            }
        }
   }
</script>
