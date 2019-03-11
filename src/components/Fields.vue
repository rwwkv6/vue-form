<template>
  <div class="fields">

    <h3>{{ fields.creatorName.label }}</h3>
    <input v-model="fields.creatorName.value" placeholder="Your Name">

    <h3>{{ fields.objectType.label }}</h3>
    <select v-model="fields.objectType.value">
      <option disabled value="">Please select one</option>
      <option v-for="choice in fields.objectType.choices">{{ choice }}</option>
    </select>

    <h3 v-if="fields.objectType.value == '3d model'">{{ fields.modelFileType.label }}</h3>
    <select v-if="fields.objectType.value == '3d model'" v-model ="fields.modelFileType.value">
      <option disabled value="">Select file type</option>v-container>
      <option v-for="choice in fields.modelFileType.choices">{{ choice }}</option>    
    </select>
  </div>
</template>

<script>
export default {
  name: 'Fields',
  props: {
    fields: Object
  }
}
</script>