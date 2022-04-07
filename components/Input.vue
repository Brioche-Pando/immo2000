<template>
  <div>
    <label :for="id">{{ label }}</label>
    <input
      :id="id"
      :type="type"
      :name="name"
      :required="required"
      :value="value"
      @input="
        $emit(
          'input',
          type === 'checkbox' ? $event.target.checked : $event.target.value
        )
      "
    />
  </div>
</template>

<script>
export default {
  props: {
    id: String,
    value: [String, Boolean],
    type: String,
    name: String,
    required: Boolean,
    label: String,
  },
};
</script>