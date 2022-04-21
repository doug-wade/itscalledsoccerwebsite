<template>
  <div>{{ JSON.stringify(value) }}</div>
</template>

<script>
export default {
  name: 'TeamGoalsAdded',
  props: {
    value: Object
  }
}
</script>
