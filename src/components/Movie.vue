<template>
    <div id="Movie">
        <form @submit.prevent='formSubmit'>
            <input type="text" v-model="movieTitle">
            <input type="submit" value="Submit">
        </form>
    </div>
</template>

<script>
export default {
    name: 'Movie',
    data: function(){
        return{
            movieTitle: ''
        }
    },
    methods: {
        formSubmit(e){
            this.$emit('formSubmit', this.movieTitle);
            e.preventDefault();
        }
    }
}
</script>

