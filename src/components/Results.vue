<template>
    <div v-if="showResults">
        <p >Reaction Time:{{score}} ms</p>
        <h2>{{result}}</h2>
    </div>
</template>


<script>
export default {
    name: 'Result',
    props: ["score","showResults"],
    computed: {
        result(){

            if(this.score <= 250){
                return "Your Got Talent Kiddo..."
            }
            else if(this.score <= 450){
                return "Wow Nigga!! That's Good..."
            }
            else{
                return "Snail Pace Nigga...."
            }
        }
    }
}
</script>



<style scoped>

</style>