<!-- HTML -->
<template>
<select name="filter-genre" id="filter-genre" >
    <option v-for="(newGenre, i) in genreArr" :v-model="newGenre" @click="$emit('filter', newGenre)" :key="i">{{newGenre.toUpperCase()}}</option>
</select>
</template>

<!-- JS -->
<script>
export default {
  name: 'MyFilters',
  data () {
    return {
        genreArr  : ['all', 'rock', 'metal', 'pop', 'jazz']
    }
  },
  created () {
    console.log(this.newGenre);
  }

}
</script>

<!-- CSS -->
<style scoped lang="scss">

</style>
