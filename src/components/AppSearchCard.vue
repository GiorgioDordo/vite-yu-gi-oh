<script>
import axios from 'axios';

export default {
  data () {
    return {
      archetypes: [],

      apiUrl: 'https://db.ygoprodeck.com/api/v7/archetypes.php',

      selectedItem: '',
    }
  },

  methods:{

    getArchetypes () {
      console.log("Chiamata API Archetypes iniziata");

      axios.get(this.apiUrl)
        .then((response) => {
          console.log(response.data);
          this.archetypes = response.data;
        })
        .catch(function (error) {
          console.log(error);
        })
        .finally(() => {
          this.loading = false;
          console.log("Chiamata API Archetypes terminata")
        });
    },

    logMessage(message){
      console.log(`message called ${message}`);

      this.$emit("archetypeSearch", message);
    },
  },

  created() {
      this.getArchetypes();
    }
}
</script>

<template>
  <div class="form-imput-group mb-5">
    <select class="form-select" @change="logMessage(selectedItem)" v-model="selectedItem">
              <option v-for="(archetype, index) in archetypes" :key="index" :value="archetype.archetype_name">
                {{ archetype.archetype_name }}
              </option>
    </select>
  </div>
</template>

<style lang="scss" scoped>

</style>
