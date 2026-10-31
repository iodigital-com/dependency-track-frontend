<template>
  <b-modal id="modal-informational" hide-header-close>
    <template v-slot:modal-title>Information</template>
    <div class="row">
      <div class="col-sm-12 col-md-12">
        <div
          class="pull-left"
          style="width: 70px; min-width: 70px; max-width: 70px"
        >
          <i class="fa fa-info-circle fa-4x" aria-hidden="true"></i>
        </div>
        <div style="overflow: hidden">
          <p>{{ message }}</p>
          <p v-if="helpUrl">
            <b-link :href="helpUrl" target="_blank" rel="noopener noreferrer">{{
              $t('message.help')
            }}</b-link>
          </p>
        </div>
      </div>
    </div>
    <template v-slot:modal-footer>
      <b-button
        class="btn btn-primary"
        @click="$bvModal.hide('modal-informational')"
        >Close</b-button
      >
    </template>
  </b-modal>
</template>

<script>
export default {
  name: 'InformationalModal',
  props: {
    message: String,
    helpUrl: String,
  },
};
</script>
