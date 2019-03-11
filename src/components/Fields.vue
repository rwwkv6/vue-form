<template>
  <div class="fields">

    <div class="form-group">
      <h4>{{ fields.creatorName.label }}</h4>
      <p v-for="creator in fields.creatorName.creators">
        <input type="text" class="form-control"
          v-model="fields.creatorName.value[creator-1]" 
          placeholder="Creator Name"
        >
      </p>
      <p>
        <button type="button" class="btn btn-info btn-sm" v-on:click="fields.creatorName.creators += 1">Add Creators</button>
      </p>
      <p>
        <button type="button" class="btn btn-danger btn-sm"
        v-if="fields.creatorName.creators > 1" 
        v-on:click="fields.creatorName.creators -= 1">Remove Creators</button>
      </p>
    </div>

    <p>
    <h4>{{ fields.objectType.label }}</h4>
    <select class="custom-select" v-model="fields.objectType.value">
      <option disabled value="">Please select one</option>
      <option v-for="choice in fields.objectType.choices">{{ choice }}</option>
    </select>
    </p>

    <p>
    <h4 v-if="fields.objectType.value == '3d model'">{{ fields.modelFileType.label }}</h4>
    <select class="custom-select" v-if="fields.objectType.value == '3d model'" v-model ="fields.modelFileType.value">
      <option disabled value="">Select file type</option>v-container>
      <option v-for="choice in fields.modelFileType.choices">{{ choice }}</option>    
    </select>
    </p>

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