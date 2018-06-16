<template>
  <card >
    <card-header v-if="cardHead"></card-header>
    <card-body>

    </card-body>
  </card>
</template>

<script>
import card from '@/components/Card';
import cardHeader from '@/components/CardHeader';
import cardBody from '@/components/CardBody';

export default {
  name: 'CardPage',
  props: {
    cardHead: {
      type: String,
      default: (() => '')
    },
    cardBody: {
      type: Object,
    },
  },
  components: {
    'Card': card,
    'CardHeader': cardHeader,
    'CardBody': cardBody
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
