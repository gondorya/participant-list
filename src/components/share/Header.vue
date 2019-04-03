<template>
  <div class="row">
    <h1 class="title">Your Participant List</h1>
    <div class="progress">
      <div class="progress">
        <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" :style="{width: (participantsCount / maxParticipants) * 100 + '%'}">
          {{ participantsCount }} / {{ maxParticipants }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['participantsCount', 'maxParticipants']
  }
</script>


<style scoped>
  .title {
    font-size: 20px;
    color: #222;
  }

  .progress {
    height: 15px;
  }
</style>
