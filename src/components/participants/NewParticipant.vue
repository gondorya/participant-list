<template>
  <div class="row">
    <div class="col-sm-8 col-sm-offset-2">
      <form>
        <label>Participant Name</label>
        <input type="text" class="form-control" v-model="person">
        <button class="btn btn-primary" @click.prevent="addNewParticipant">Add new participant</button>
      </form>
    </div>
  </div>

</template>

<script>
  export default {
    data: () => {
      return {
        person: ''
      }
    },
    methods: {
      addNewParticipant() {
        this.$emit('participantAdded', this.person);
        this.person = '';
      }
    }
  }
</script>

<style scoped>
  form {
    margin: 20px 0;
  }

  .btn {
    margin: 15px 0 0;
  }
</style>
