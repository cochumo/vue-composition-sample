<template>
  <div>
    <h2>CompositionComponents</h2>
    <p>user: {{ user }}</p>
  </div>
</template>

<script>
export default {
  props: {
    user: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    console.log(props); // { user: '' }

    return {}; // anything returned here will be available for the rest of the component
  },
};
</script>

<style></style>
