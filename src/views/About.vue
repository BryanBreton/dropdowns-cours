<template>
  <div class="about">
    <div v-for="data in dropdown_datas" :key="data.id">
      <v-card class="pa-md-4 ma-4 mx-lg-auto">
        <v-card-title>
          {{ data.title }}
        </v-card-title>
        <v-card-text>
          {{ data.content }}
        </v-card-text>
        <!-- au moment du clic on change la valeur de vision ou non -->
        <v-btn icon @click="changeStatus(data.id)">
          <v-icon>{{
            dropdown_status[data.id] ? "mdi-chevron-up" : "mdi-chevron-down"
          }}</v-icon>
        </v-btn>
        {{dropdown_status[data.id -1].show}}
        <div>
          <div v-show="dropdown_status[data.id -1].show">
            <v-card-text>
              ouiiiiiiiiiiiiiiiiiiiiiiiiiii
            </v-card-text>
          </div>
        </div>
      </v-card>
    </div>
    <v-btn @click="aide()"></v-btn>
  </div>
</template>


<script>
import datas from '../../datas.json'
export default {
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
        this.dropdown_status.push({show: false})
      })
      console.log(this.dropdown_status)
    },
    methods:{
      aide(){
        console.log(this.dropdown_status)
      },
      changeStatus(id){
        console.log(this.dropdown_status[id-1].show)
        this.dropdown_status[id-1].show = !this.dropdown_status[id-1].show
        console.log(this.dropdown_status[id-1].show)
      }
    }
}
</script>