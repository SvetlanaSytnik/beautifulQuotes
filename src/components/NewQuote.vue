<template>
  <div class="row">
    <form action="post">
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <label for="quote">Quote</label>
        <textarea class="form-control" name="quote" id="quote" v-model="quote" cols="30" rows="3"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>

export default {
  data: function() {
    return {
      quote: ''
    }
  },
  methods: {
    createNew() {
      this.$emit('quoteAdded', this.quote);
      this.quote = '';
    }
  }
}
</script>

<style>
  label {
    padding-top:  30px;
  }

  textarea {
    margin-bottom: 20px;
  }

  button.btn {
    margin-bottom: 30px;
  }
</style>