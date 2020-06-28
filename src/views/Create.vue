<template>
  <div class="row">
    <div class="col s6 offset-s3">
      <h1>Create Task</h1>
      <form>
        <div class="input-field col-12">
          <input v-model="title" id="title" type="text" class="validate" required>
          <label for="title">Title</label>
          <span class="helper-text" data-error="Title is required"></span>
        </div>
        <div class="chips col-12" ref="chips"></div>

        <div class="input-field col-12 s12">
          <textarea v-model="description" id="description" class="materialize-textarea"></textarea>
          <label for="description">Textarea</label>
          <span class="character-counter" style="float: right; font-size: 12px;">{{description.length}}/2048</span>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: 'Create',
  data: () => ({
    description: ''
  }),
  mounted() {
    M.Chips.init(this.$refs.chips, {
      placeholder: 'Task tags'
    });
  }
}
</script>
