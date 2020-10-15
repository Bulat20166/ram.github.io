<template>
    <div class="character-block">
        <div class="character-block__image">
            <img :src="character.image" :alt="character.name" width="160px" height="auto">
        </div>
        <div class="character-block__info">
            <a href="" style="color:blue" @click="detailedInfo">
                {{character.name}}
            </a>   
            <span>
                {{character.status}} - {{character.species}}
            </span>     
            <span>
                Last know location {{character.location.name}}
            </span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'character-block',
    props: {
        character: {
            type: Object,
            required: true,
        }
    },
    methods: {
        detailedInfo () {
            this.$router.push({name: 'CharacterDetails', params: {id: this.character.id}})
        }
    }
    
}
</script>