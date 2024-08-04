<template>
  <div>
    <label :for="id">{{ label }}</label>
    <input
      :id="id"
      :type="type"
      :value="modelValue"
      :placeholder="placeholder"
      @input="$emit('update:modelValue', $event.target.value)"
    />
  </div>
</template>

<script>
export default {
  name: "TextInput",
  props: {
    modelValue: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      default: "",
    },
    id: {
      type: String,
      default: "",
    },
    type: {
      type: String,
      default: "text",
    },
    placeholder: {
      type: String,
      default: "",
    },
  },
  emits: ["update:modelValue"],
};
</script>

<style scoped>
/* Add your styles here */
</style>

<!-- todo parent
<template>
  <div>
    <TextInput
      v-model="textInputValue"
      label="Enter your name"
      id="name"
      placeholder="Name"
    />
    <p>Your input: {{ textInputValue }}</p>
  </div>
</template>

<script>
import TextInput from './TextInput.vue';

export default {
  components: {
    TextInput,
  },
  data() {
    return {
      textInputValue: '',
    };
  },
};
</script> -->
