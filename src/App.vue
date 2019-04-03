<template>
  <div class="container">
    <app-header :participantsCount="people.length" :maxParticipants="maxParticipants"></app-header>
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
  import Header from './components/share/Header';

  export default {
    components: {
      appParticipantList: ParticipantList,
      appNewParticipant: NewParticipant,
      appHeader: Header
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
        if(this.people.length >= this.maxParticipants) {
          return alert('Please delete participants first');
        } else {
          this.people.push(person);
        }
      },
      deleteParticipant(index) {
        this.people.splice(index)
      }
    }
  }
</script>

