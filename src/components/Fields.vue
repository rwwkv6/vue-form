<template>
  <div class="fields">

    <h4>{{ fields.creatorName.label }}</h4>
      <input 
        v-for="creator in fields.creatorName.creators" 
        v-model="fields.creatorName.value[creator-1]" 
        placeholder="Creator Name"
      >
      <button 
        v-if="fields.creatorName.creators > 1" 
        v-on:click="fields.creatorName.creators -= 1">-</button>
      <button v-on:click="fields.creatorName.creators += 1">+</button>

    <h4>{{ fields.objectType.label }}</h4>
    <select v-model="fields.objectType.value">
      <option disabled value="">Please select one</option>
      <option v-for="choice in fields.objectType.choices">{{ choice }}</option>
    </select>
    <br>

    <h4 v-if="fields.objectType.value == '3d model'">{{ fields.modelFileType.label }}</h4>
    <select v-if="fields.objectType.value == '3d model'" v-model ="fields.modelFileType.value">
      <option disabled value="">Select file type</option>v-container>
      <option v-for="choice in fields.modelFileType.choices">{{ choice }}</option>    
    </select>
    <br>

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

<style>

</style>