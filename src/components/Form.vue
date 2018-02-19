<template>
  <div class="container">
      <div class="panel panel-primary">
        <div class="panel-heading">
           Add Network
        </div>
        <div class="panel-body">
          <form novalidate>
            <div class="form-group">
              <label>Network Name</label>
              <input type="text" name="name"/>
            </div>
            <div class="form-group">
              <label>Network Bandwidth</label>
              <input type="text" name="bandwidth"/>
            </div>
            <div>
              <button  class="btn btn-primary">Add</button>
            </div>
          </form>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'FormTest',
  data () {
    return {
      name: '',
      bandwidth: ''
    }
  },
  computed: {
    isComplete () {
      return this.name && this.bandwidth
    }
  },
  methods: {
    validateBeforeSubmit () {
      this.$validator.validateAll().then((result) => {
        if (result) {
          alert('From Submitted!')
        }
      })
    }
  }
}
</script>