<template>
  <div class="container">
    <app-new-participant @participantAdded="newPerson($event)"></app-new-participant>
    <app-participant-list :participants="people" @participantDeleted="deleteParticipant($event)"></app-participant-list>
    <div class="row">
      <div class="col text-center">
        <div class="alert alert-info">
          Info: Click on Participant to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import ParticipantList from './components/participants/ParticipantList';
  import NewParticipant from './components/participants/NewParticipant';

  export default {
    components: {
      appParticipantList: ParticipantList,
      appNewParticipant: NewParticipant,
    },
    data: () => {
      return {
        people: [
          'Example Person'
        ],
        maxParticipants: 20,
      }
    },
    methods: {
      newPerson(person) {
        this.people.push(person)
      },
      deleteParticipant(index) {
        this.people.splice(index)
      }
    }
  }
</script>

