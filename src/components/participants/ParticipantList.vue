<template>
  <div>
     <ul class="list-group">
       <app-participant v-for="(participant, index) in participants" @click.native="deleteParticipant(index)">{{ participant }}</app-participant>
     </ul>
  </div>
</template>

<script>
  import Participant from './Participant';

  export default {
    props: ['participants'],
    components: {
      appParticipant: Participant,
    },
    methods: {
      deleteParticipant(index) {
        this.$emit('participantDeleted', index);
      }
    }
  }
</script>
