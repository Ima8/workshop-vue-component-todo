<template>
  <div>
    <h2>{{hero.name}} details!</h2>
    <div>
      <label>id: </label>{{hero.id}}</div>
    <div>
      <label>name: </label>
      <input v-model="hero.name" @change="onChange" placeholder="name">
    </div>
  </div>
</template>

<script>
export default {
  props: ['hero'],
  data() {
    return {
      tmpName: ""
    }
  },
  methods: {
    onChange() {
      setTimeout(() => {
        this.$emit('changeNameHero', "This is real name")
      }, 1000);
      this.$emit('updateMessage','New name is '+this.hero.name)
    }
  }
}
</script>


<style scoped>
.selected {
  background-color: #CFD8DC !important;
  color: white;
}

.heroes {
  margin: 0 0 2em 0;
  list-style-type: none;
  padding: 0;
  width: 15em;
}

.heroes li {
  cursor: pointer;
  position: relative;
  left: 0;
  background-color: #EEE;
  margin: .5em;
  padding: .3em 0;
  height: 1.6em;
  border-radius: 4px;
}

.heroes li.selected:hover {
  background-color: #BBD8DC !important;
  color: white;
}

.heroes li:hover {
  color: #607D8B;
  background-color: #DDD;
  left: .1em;
}

.heroes .text {
  position: relative;
  top: -3px;
}

.heroes .badge {
  display: inline-block;
  font-size: small;
  color: white;
  padding: 0.8em 0.7em 0 0.7em;
  background-color: #607D8B;
  line-height: 1em;
  position: relative;
  left: -1px;
  top: -4px;
  height: 1.8em;
  margin-right: .8em;
  border-radius: 4px 0 0 4px;
}
</style>
