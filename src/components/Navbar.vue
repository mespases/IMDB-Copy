<script setup>

</script>

<template>
    <nav>
        <div class="logo">
            <router-link :to="'/'"><img src="@/assets/img/logo.png" alt="logo"></router-link>
        </div>
        <div class="search_bar">
            <form action="index.php" method="GET">
                <input type="text" name="search">
                <button type="submit" class="btn btn-success transparetn">
                    <i class="fas fa-search"></i> Buscar
                </button>
            </form>
        </div>
    </nav>
</template>

<style scoped>
    nav {
        background-color: #121212;
        display: flex;
        align-items: center;
    }

    nav div.logo {
        width: 15%;
        margin-right: 10em;
    }

    nav div.logo img {
        width: 95px;
        margin-left: 4em;
        margin-top: 0.2em;
    }

    nav div.search_bar {
        width: 50%;
    }

    nav div.search_bar input {
        width: 90%;
        height: 20px;
        border-radius: 7px;
    }

    nav div.search_bar button i {
        cursor: pointer;
    }
</style>