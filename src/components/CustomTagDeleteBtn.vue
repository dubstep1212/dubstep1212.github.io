<template>
  <el-popover :title="`${$t('areYouSure')}？`" placement="right">
    <i v-show="visible" slot="reference" class="fa fa-times-circle" aria-hidden="true" @click.stop="handleDeleteTag"></i>
    <footer class="popover-footer">
      <el-button size="mini" @click="handleCancelDeleteTag">{{ $t('no') }}</el-button>
      <el-button type="primary" size="mini" @click="handleConfirmDeleteTag">{{ $t('yes') }}</el-button>
    </footer>
  </el-popover>
</template>

<script>
export default {
  name: 'custom-tag-nav',
  props: {
    tag: { type: Object, required: true },
    visible: { type: Boolean, default: false },
  },
  methods: {
    handleDeleteTag () {
      document.body.click()
    },
    handleCancelDeleteTag () {
      document.body.click()
    },
    handleConfirmDeleteTag () {
      document.body.click()
      this.$store.dispatch('tag/deleteTag', this.tag.id)
    },
  },
}
</script>

<style scoped>
.fa-times-circle {
  font-size: 16px;
  transition: all 0.1s;
  cursor: pointer;
}

.fa-times-circle:hover {
  transform: scale(1.5);
}
</style>
