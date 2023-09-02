<script scope>
    export default {
        props: ['item']
    }
</script>

<template>
    <div class="film_box">
        <router-link :to="'/movie/' + item.title" class="overlay">
            <i class="fas fa-play"></i>
        </router-link>
        
        <div class="img_box">
            <img :src="'img_films/' + item.image" />
        </div>
        <router-link :to="'/movie/' + item.title">
            <div class="text_box">
                <span class="puntuacion">{{item.score}}</span>
                <div class="bottom">
                    <div class="movie_name">
                        <span>{{item.year}}</span>
                        <strong>{{item.title}}</strong>
                    </div>
                </div>
            </div>
        </router-link>
    </div>
</template>

<style scoped>

</style>