<template>
    <transition name="modal">
        <div class="modal-mask">
          <div class="modal-wrapper">
            <div class="modal-container">
<!-- modal head -->
              <div class="modal-header">
                <slot name="header">
                  default header
                </slot>
              </div>
<!-- modal body -->
              <div class="modal-body">
                <slot name="body">
                  default body
                </slot>
              </div>
<!-- modal footer -->
              <div class="modal-footer">
                <slot name="footer">
                  default footer
                  <button class="modal-default-button" @click="$emit('close')">
                    OK
                  </button>
                </slot>
              </div>
            </div>
          </div>
        </div>
      </transition>
      
</template>

<script>
export default {
    
}

</script>

<style scoped>
modal {
    background-color: gray;
}

</style>