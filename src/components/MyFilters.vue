<!-- HTML -->
<template>
<select name="filter-genre" id="filter-genre" v-model="varGenre" @change="$emit('filter', varGenre)" >
    <option v-for="(newGenre, i) in genreArr" :value="newGenre" :key="i">{{newGenre.toUpperCase()}}</option>
</select>
</template>

<!-- JS -->
<script>
export default {
  name: 'MyFilters',
  data () {
    return {
        genreArr  : ['all','rock', 'metal', 'pop', 'jazz'],
        varGenre : 'all',
    }
  }

}
</script>

<!-- CSS -->
<style scoped lang="scss">

</style>
