<template>
  <Wrap :page="page" :showLeftbar="false">
    <div class="page-title">{{ page.attributes.title }}</div>
    <div class="page-content">
      <slot name="default"/>
    </div>
  </Wrap>
</template>

<script>
import Wrap from '../components/Wrap.vue'
import DocMixin from '../mixins/doc'

export default {
  components: {
    Wrap
  },

  props: ['page'],

  mixins: [DocMixin],

  head() {
    return {
      title: `${this.page.attributes.title} - Saber`
    }
  }
}
</script>
