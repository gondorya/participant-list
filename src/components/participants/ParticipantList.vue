<template>
  <div>
     <ul class="list-group">
       <app-participant v-for="participant in participants">{{ participant }}</app-participant>
     </ul>
  </div>
</template>

<script>
  import Participant from './Participant';

  export default {
    props: ['participants'],
    components: {
      appParticipant: Participant,
    }
  }
</script>
