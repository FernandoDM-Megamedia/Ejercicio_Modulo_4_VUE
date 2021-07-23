<template>
  <Header />
  <!-- <Form /> -->
  <Display />
  <router-view />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Header from '@/components/Header.vue'
// import Form from '@/components/form.vue'
// import Display from '@/components/display.vue'
// import VueDataTable from '@/components/VueDataTable.vue'

export default defineComponent({
  components: {
    Header,
    // Form,
    // Display,
    // VueDataTable,
  },
})
</script>
