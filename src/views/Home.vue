<template>
<div class="home">
  <v-expansion-panels>
    <v-expansion-panel
      v-for="item in dropdown_datas"
      :key="item.id"
    >
      <v-expansion-panel-header>
        {{item.title}}
      </v-expansion-panel-header>
      <v-expansion-panel-content>
        {{item.content}}
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-expansion-panels>
</div>
</template>

<script>
  import datas from '../../datas.json'
  export default {
    name: 'Home',
    data(){
      return {
        dropdown_datas: [],
        dropdown_status: []
      }
    },
    created(){
      this.dropdown_datas = datas
      this.dropdown_datas.forEach(() => {
        console.log('un tour')
        this.dropdown_status.push(false)
      })
      console.log(this.dropdown_status)
    },
    components: {
    },
  }
</script>
