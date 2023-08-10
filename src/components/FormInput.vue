<template>
  <label class="input-label">{{ fieldLabel }}</label>
  <input
    class="input-field"
    :name="fieldName"
    :type="fieldtype"
    :placeholder="fieldPlaceholder"
  />
</template>

<script>
export default {
  name: "FormInput",
  props: {
    fieldProperties: {
      type: Object,
      validator: (propertyObj) => {
        if (
          !propertyObj.hasOwnProperty("label") ||
          !propertyObj.hasOwnProperty("name") ||
          !propertyObj.hasOwnProperty("type") ||
          !propertyObj.hasOwnProperty("placeholder")
        ) {
          return false;
        } else if (
          typeof propertyObj.label !== "string" ||
          typeof propertyObj.name !== "string" ||
          typeof propertyObj.type !== "string" ||
          typeof propertyObj.placeholder !== "string"
        ) {
          return false;
        } else if (
          !propertyObj.label.length ||
          !propertyObj.name.length ||
          !propertyObj.type.length ||
          !propertyObj.placeholder.length
        ) {
          return false;
        } else {
          return true;
        }
      },
    },
  },
  computed: {
    fieldLabel() {
      return this.fieldProperties.label;
    },
    fieldName() {
      return this.fieldProperties.name;
    },
    fieldtype() {
      return this.fieldProperties.type;
    },
    fieldPlaceholder() {
      return this.fieldProperties.placeholder;
    },
  },
};
</script>

<style scoped>
.input-label {
  display: inline-block;
  margin-bottom: 10px;
  font-size: 25px;
  font-weight: bold;
}

.input-field {
  font-size: 25px;
  display: block;
  width: 300px;
  color: gray;
  border: 2px solid black;
  border-radius: 10px;
  padding: 5px;
}
</style>
