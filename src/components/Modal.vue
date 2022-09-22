<template>
    <div class="modal flex">
        <div class="modal-content">
            <p>Are you sure you want to exit? Your changes will not be saved</p>
            <div class="action-flex">
                <button @click="closeModal" class="purple">Return</button>
                <button @click="closeInvoice" class="red">close</button>
            </div>
        </div>
    </div>
</template>

<script>
   import { mapMutations } from 'vuex';
    export default {
        name:"Modal-vue",
        methods:{
          ...mapMutations(["TOGGLE_MODAL", "TOGGLE_INVOICE"]),

          closeModal(){
            this.TOGGLE_MODAL();
          },

          closeInvoice(){
            this.TOGGLE_MODAL();
            this.TOGGLE_INVOICE();
          }


        }
        
    }
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Alumni+Sans+Inline+One:ital@0;1&display=swap");

.modal {
  z-index: 100;
  position: fixed;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;

  .modal-content {
    border-radius: 20px;
    padding: 48px 32px;
    max-width: 450px;
    background-color: #252945;
    color: #fff;

    p {
      text-align: center;
    }

    .actions {
      margin-top: 24px;
      button {
        flex: 1;
      }
    }
  }
}
</style>