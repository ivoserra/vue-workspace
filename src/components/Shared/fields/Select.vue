<template>
  <div>
    <label :for="id">{{ label }}</label>
    <select
      :id="id"
      :value="modelValue"
      @change="$emit('update:modelValue', $event.target.value)"
    >
      <option
        v-for="option in options"
        :key="option.value"
        :value="option.value"
      >
        {{ option.text }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "SelectInput",
  props: {
    modelValue: {
      type: [String, Number],
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
    options: {
      type: Array,
      required: true,
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
    <SelectInput
      v-model="selectedValue"
      label="Choose a fruit"
      id="fruit"
      :options="fruitOptions"
    />
    <p>Selected: {{ selectedValue }}</p>
  </div>
</template>

<script>
import SelectInput from './SelectInput.vue';

export default {
  components: {
    SelectInput,
  },
  data() {
    return {
      selectedValue: '',
      fruitOptions: [
        { text: 'Apple', value: 'apple' },
        { text: 'Banana', value: 'banana' },
        { text: 'Cherry', value: 'cherry' },
      ],
    };
  },
};
</script> -->
