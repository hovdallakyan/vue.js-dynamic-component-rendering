<template>
  <div>
    <h1>Video</h1>
    <button @click="onHandleClick()">Do something from parent</button>
  </div>
</template>

<script>
export default {
  name: 'videos',
  props: ['data'],
  methods: {
    onHandleClick: function() {
      console.log('methods', this.data.fc())
    }
  }
}
</script>
