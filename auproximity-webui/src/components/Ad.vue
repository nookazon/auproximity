<template>
  <div className="vm-placement" :data-id="placementId" ref="adPlacement"></div>
</template>
<script>
export default {
  props: ['placementId'],
  mounted: function () {
    this.$nextTick(function () {
      window.top.__vm_add = window.top.__vm_add || []
      window.top.__vm_add.push(this.$refs.adPlacement)
    })
  },
  beforeDestroy() {
    window.top.__vm_remove = window.top.__vm_remove || []
    window.top.__vm_remove.push(this.$refs.adPlacement)
  }
}
</script>
