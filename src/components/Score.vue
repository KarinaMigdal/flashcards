<template>
        <div v-if="game.showScore" :class="{ 'show-score' : game.showScore }" >
            <section>
                <img 
                src="../assets/fi-rr-trophy.svg" 
                alt="trophy" 
                class="icon-score">
                <div>
                    <h1>Score: {{ game.score }} / {{ game.randomFlashcards.length }}</h1>
                </div>
                <button class="btn button-ok" @click="hideScore">OK</button> 
            </section>
        </div>
   
</template>

<script>
import { mapState, mapMutations } from 'vuex'
export default {
    name:'Score',
    computed: {...mapState([ 'game',  ])},
    methods: {...mapMutations([ 'hideScore',  ]) }
    
}
</script>

<style>
.icon-score {
    height: 50px;
}

.show-score {
    border-radius: 30px;
    width: 600px;
    height: 490px;
    position: absolute;
    z-index: 10;
    border: 1px solid rgb(182, 182, 182);
    background-color: white; 
    background: linear-gradient( to right bottom, rgba(255, 255, 255, 1), rgba(255, 255, 255, 1) );
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-content: center;
}

.button-ok {   
    font-size: 25px; 
    width: 70%;
    margin: 25px auto;
    padding: 15px 0px; 
}

@media screen  and (max-width: 1000px) {
    .show-score {
        min-width: 350px;
        width: 100%;
    }
}
</style>