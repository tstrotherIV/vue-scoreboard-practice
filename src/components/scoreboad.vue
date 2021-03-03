<template>
  <div>
    <div>
      <div class="header">
        <span :class="{ winning: teams[0].score > teams[1].score }"
          >Team 1</span
        >
        <span> vs </span>
        <span :class="{ winning: teams[1].score > teams[0].score }"
          >Team 2</span
        >
      </div>
    </div>
    <h3 class="white grey">{{ whosWinning }}</h3>
    <div class="teams">
      <div v-for="team in teams" :key="team.id">
        <ScoreboardCard
          :team="team"
          @increase-score="increaseScore"
          @decrease-score="decreaseScore"
        />
      </div>
    </div>
  </div>
</template>

<script>
import ScoreboardCard from "./scoreboard_card";
import { teams } from "../data";

export default {
  components: {
    ScoreboardCard,
  },
  data() {
    return {
      teams: [...teams],
    };
  },
  methods: {
    increaseScore(team) {
      team.score += 1;
    },
    decreaseScore(team) {
      if (!team.score == 0) {
        team.score -= 1;
      }
    },
  },
  computed: {
    whosWinning() {
      if (teams[0].score > teams[1].score) {
        const score = teams[0].score - teams[1].score;
        return `Team 1 is leading by ${score}`;
      } else if (teams[0].score < teams[1].score) {
        const score = teams[1].score - teams[0].score;
        return `Team 2 is leading by ${score}`;
      }
      return "The game is currently tied";
    },
  },
};
</script>

<style>
.winning {
  color: yellow;
}
span {
  color: white;
}
.white {
  color: white;
}
.teams {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
.header {
  font-size: 120px;
}
.grey {
  color: rgb(157, 154, 154);
}
.space {
  margin: 10px;
}
</style>
