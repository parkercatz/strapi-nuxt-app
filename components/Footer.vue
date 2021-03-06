<template>
  <v-footer
    >created by ParkerCatz. ©{{ copyright }} .All Rights Reserved.</v-footer
  >
</template>
<script>
export default {
  data() {
    return {
      copyright: new Date().getFullYear(),
    }
  },
}
</script>
