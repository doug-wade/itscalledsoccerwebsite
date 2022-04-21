<template>
  <h1>Team goals added</h1>
  <TeamGoalsAdded v-for="team in teamsGoalsAdded" :value="team" :key="team.team_id"/>
</template>

<script>
import TeamGoalsAdded from './components/TeamGoalsAdded.vue'
import Client from 'itscalledsoccer'

const client = new Client();

export default {
  name: 'ItsCalledSoccerWebsite',
  components: {
    TeamGoalsAdded
  },
  async mounted() {
    this.teamsGoalsAdded = await client.getTeamsGoalsAdded({
      zone: 27,
    });
  },
  data() {
    return {
      teamGoalsAdded: []
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
