<script>
export default {
  data () {
    return {
        searchedString:"",
    }
  },
  methods: {
    searchCards(message){
        console.log(message);
        this.$emit("searchCard", message)
    }
  }
  
}
</script>

<template>
<div class="container d-flex justify-content-center mb-5">
    <form>
    <select name="archetypes" v-model="searchedString" @click="searchCards(searchedString)">
            <option value="">Select an archetype</option>
            <option value="albaz">Albaz</option>
            <option value="abyss-actor">Abyss Actor</option>
            <option value="adamancipator">Adamancipator</option>
            <option value="adventurer-token">Adventurer Token</option>
            <option value="aesir">Aesir</option>
            <option value="agent">Agent</option>
            <option value="alien">Alien</option>
            <option value="ally-of-justice">Ally of Justice</option>
            <option value="altergeist">Altergeist</option>
            <option value="amazemment">Amazemment</option>
            <option value="amazoness">Amazoness</option>
            <option value="amorphage">Amorphage</option>
            <option value="ancient-gear">Ancient Gear</option>
            <option value="ancient-warriors">Ancient Warriors</option>
            <option value="appliancer">Appliancer</option>
            <option value="aquaactress">Aquaactress</option>
            <option value="arcana-force">Arcana Force</option>
            <option value="archfiend">Archfiend</option>
            <option value="armed-dragon">Armed Dragon</option>
            <option value="aroma">Aroma</option>
            <option value="artifact">Artifact</option>
            <option value="ashened">Ashened</option>
            <option value="assault-mode">Assault Mode</option>
            <option value="atlantean">Atlantean</option>
            <option value="a-to-z">A-to-Z</option>
            <option value="batteryman">Batteryman</option>
            <option value="battlewasp">Battlewasp</option>
            <option value="battlin-boxer">Battlin Boxer</option>
            <option value="beetrooper">Beetrooper</option>
            <option value="black-luster">Black Luster</option>
            <option value="blackwing">Blackwing</option>
            <option value="blue-eyes">Blue-Eyes</option>
            <option value="bounzer">Bounzer</option>
            <option value="bujin">Bujin</option>
            <option value="burning-abyss">Burning Abyss</option>
            <option value="buster-blader">Buster Blader</option>
            <option value="butterspy">Butterspy</option>
            <option value="bystial">Bystial</option> 
    </select>
    <input type="submit" value="Reset">   
    </form>
</div>
</template>

<style lang="scss" scoped>

</style>
