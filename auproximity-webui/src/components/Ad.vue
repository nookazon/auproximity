<template>
  <div className="vm-placement" :data-id="placement" ref="adPlacement"></div>
</template>
<script>
export default {
  props: ['name'],
  data: () => ({
    placement: '5f7c39e15c013163f93ea7c6'
  }),
  beforeMount() {
    if (this.name === 'top') {
      this.placement =
        window.innerWidth < 600
          ? '5f7c394bda7a8f6d26edd47d'
          : '5f77421c5c013163f93ea725'
    } else {
      this.placement =
        window.innerWidth < 600
          ? '5f7c39e15c013163f93ea7c6'
          : '5f77424b5c013163f93ea727'
    }
  },
  mounted() {
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
