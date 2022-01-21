<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale'}">
           <slot></slot>
           <div class="actions">
               <slot name="links"></slot>
           </div>
        </div>
    </div>
</template>

<script>
export default {
  props: ['theme'],
  methods: {
      closeModal(){
          this.$emit('close')
      }
  },
}
</script>

<style>
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: whitesmoke;
        border-radius: 10px;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background: rgb(0,0,0,0.5);
        width: 100%;
        height: 100%;
    }
    .modal.sale{
        background: seagreen;
        color: whitesmoke;
    }
    .modal.sale h1{
        color: whitesmoke;
    }
    .modal .actions{
        text-align: center;
        margin: 30px 0 10px 0;
        color: whitesmoke;
    }
    .modal .actions a{
        color: whitesmoke;
        padding: 8px;
        border: 1px solid whitesmoke;
        border-radius: 4px;
        text-decoration: none;
        margin: 10px;
    }
</style>