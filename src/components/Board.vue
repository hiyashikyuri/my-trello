<template>
  <div>
    <header>
      my Trello
    </header>
    <main>
      <p class="info-line">All: 0 tasks</p>
      <list v-for="(item, index) in lists"
            :key="item.id"
            :title="item.title"
            :listIndex="index"
      />
      <list-add />
    </main>
  </div>
</template>

<script>
  import List from './List'
  import ListAdd from "./ListAdd"
  import { mapState } from 'vuex'

  export default {
    components: {
      List,
      ListAdd
    },

    computed: {
      ...mapState([
        'lists'
      ])
    }
  }

</script>
