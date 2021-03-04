<template>
  <div>
    <div @click="open">
      <button class="button is-primary">Click me</button>
    </div>

    <modals :open="isOpen"></modals>

  </div>
</template>

<script>

  import Modal from "./Modal";
  import Modals from "./Modals";

  export default {
    components: {Modals, Modal},
    created() {
      window.eventBus.$on('close', () => {
        this.isOpen = false;
      })
    },
    data(){
      return {
        isOpen: false
      }
    },
    methods: {
      open(event){
        console.log(event);
        if(event.target.localName=== 'button') {
          this.isOpen = true;
        }
      }
    }
}
</script>

