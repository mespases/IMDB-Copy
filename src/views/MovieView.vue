<script scope>
    import { RouterLink, RouterView } from 'vue-router'
    import jsonData from '@/assets/json/films.json'

    export default {
        data() {
            return {
                slug: null,
                movie: null,
            };
        },
        created() {
            this.slug = this.$route.params.slug;
            this.loadMovieData();
        },
        methods: {
            loadMovieData() {
                this.movie = jsonData.find(movie => movie.title === this.slug);
            },
        },
    };
</script>

<template>
    <div class="content">
        <div class="trailer">
            <iframe :src="movie.trailer + '?autoplay=1&mute=1'" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <!-- ?autoplay=1&mute=1 -->
        </div>
        <div class="right">
            <div class="top">
                <img :src="'/img_films/' + movie.image" :alt="movie.title" />
                <h5>{{movie.title}} ({{movie.year}}) <i class="fas fa-star amarillo"></i><p class="val w">/10</p><p class="val">{{movie.score}}</p></h5>
                <p class="line">Genero:</p> 
                <p>
                    <span v-for="(genre, index) in movie.genres" :key="index">
                        {{ genre }}<span v-if="index < movie.genres.length - 1">, </span>
                    </span>
                </p>
            </div>
            <hr>
            <div class="bottom">
                <h5 class="white">Director:</h5>
                <h5>
                    <span v-for="(directors, index) in movie.director" :key="index">
                        {{ directors }}<span v-if="index < movie.director.length - 1">, </span>
                    </span>
                </h5>
                <h5 class="white">Actores: </h5>
                <h5>
                    <span v-for="(actor, index) in movie.actors" :key="index">
                        {{ actor }}<span v-if="index < movie.actors.length - 1">, </span>
                    </span>
                </h5>
            </div>
        </div>

    </div>

    <!-- Slider -->
    <!--<div class="slider">
        <ul id="autoWidth" class="cs-hidden">

            <?php foreach ($slider as $i) {?>
                <li>
                    <div class="film">
                        <a href="singlePage.php?id=<?php echo $i->getId(); ?>"><img src="<?php echo "img/".$i->getImagen(); ?>" alt="<?php echo $i->getTitulo(); ?>" style="width: 300px"></a>
                    </div>
                </li>
            <?php } ?>
            
        </ul>
    </div>-->

    <!--<section class="comments">
        <h3>Comentarios</h3>

        <?php if (!isset($_SESSION["loggedIn"]) || !$_SESSION["loggedIn"]) { ?>
            <form action="#" method="POST">
                <textarea placeholder="Añade un nuevo comentario" rows="4" cols="10" maxlength="255" readonly id="text"></textarea>
                <div class="comment_btn">
                    <button>Publicar</button>
                </div>
            </form>
        <?php } else { ?>
            <form action="comentPOST.php" method="POST">
                <textarea placeholder="Añade un nuevo comentario" rows="4" cols="10" maxlength="255" name="coment"></textarea>
                <div class="comment_btn">
                    <div class="puntuation">
                        <label class="like">
                            <input type="radio" name="like" value="+1" checked>
                            <i class="fas fa-thumbs-up"></i>
                        </label>
                        <label class="dislike">
                            <input type="radio" name="like" value="-1">
                            <i class="fas fa-thumbs-down"></i>
                        </label>
                    </div>
                    <button>Publicar</button>
                </div>
            </form>
         <?php } ?>-->

        <!-- Lista de comentarios
        <p>Comentarios más recientes</p>
        <hr/>
        <ul class="comment_list" style="color: white">

            <?php
                foreach ($peli->getComentarios() as $comentario) {
            ?>
            <li>
                <article>
                    <i class="fas fa-user-circle"></i>
                    <?php
                    if ($comentario->getPuntuacion() == "+1") {
                        echo '<i class="fas fa-thumbs-up"></i>';
                    } else {
                        echo '<i class="fas fa-thumbs-down"></i>';
                    }
                    ?>
                    <div class="text">
                        <h4><?php echo $comentario->getNombre(); ?></h4>
                        <p><?php echo $comentario->getCommentario(); ?></p>
                    </div>
                </article>
            </li>
            <?php } ?>
        </ul>
    </section> -->
</template>