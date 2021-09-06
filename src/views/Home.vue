<template>
<div class="home">
  
<v-expansion-panels>
  <v-expansion-panel v-for="data in dropdown_datas" :key="data.id">
<v-expansion-panel-header>
{{data.title}}
</v-expansion-panel-header>
<v-expansion-panel-content>
{{data.content}}
</v-expansion-panel-content>
  </v-expansion-panel>
</v-expansion-panels>

</div>
</template>

<script>
import datas from "../../datas.json"

  export default {
   data(){
     return {
       dropdown_datas : [],
       dropdown_status : [],
     }
    }, 
    created() {
      this.dropdown_datas = datas
      this.dropdown_datas.forEach(()=> {
        this.dropdown_status.push({show : false})
      })
      console.log(this.dropdown_status)
   }
    
  }
</script>
