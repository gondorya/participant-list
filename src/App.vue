<template>
  <div class="container">
    <app-new-participant @participantAdded="newPerson($event)"></app-new-participant>
    <app-participant-list :participants="people"></app-participant-list>
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
        maxQuotes: 20,
      }
    },
    methods: {
      newPerson(person) {
        this.people.push(person)
      }
    }
  }
</script>

