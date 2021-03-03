<template>
  <div class="team">
    <div>
      <div>
        <div class="white space fontSize">{{ team.score }}</div>
      </div>
      <div class="scoreButtons">
        <button class=" subtractButton" @click="doSomething" value="-">
          -
        </button>
        <button class=" addButton" @click="doSomething" value="+">+</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    doSomething(e) {
      e.target.value === "+"
        ? this.$emit("increase-score", this.team)
        : this.$emit("decrease-score", this.team);
    },
  },
  props: ["team"],
};
</script>

<style >
.white {
  color: white;
}
.team {
  height: 300px;
  width: 300px;
  border: 10px solid white;
  display: flex;
  justify-content: center;
  align-items: center;
}

.space {
  margin: 4px;
}

.fontSize {
  font-size: 100px;
}

.addButton {
  background-color: rgba(0, 128, 0, 0.194);
  width: 100px;
  height: 50px;
  color: white;
  font-size: 30px;
  border: 2px solid green;
}

.subtractButton {
  background-color: rgba(255, 0, 0, 0.194);
  width: 100px;
  height: 50px;
  color: white;
  font-size: 30px;
  border: 2px solid red;
}
</style>
