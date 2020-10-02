<template>
  <div>
    <h1>รายละเอียดสินค้า</h1>
    <h2>สินค้าหมายเลข {{ this.$route.parms.id}}</h2>
    <h3>{{ id }}</h3>
  </div>
</template>

<script>
export default {
    data() {
        return {
            id: this.$route.parms.id,
        }
    },
}
</script>
