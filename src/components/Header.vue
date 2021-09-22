<template>
    <header>
        <div id="logo">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/1024px-Spotify_logo_without_text.svg.png" alt="Logo Spotify">
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style lang="scss" scoped>
    @import '../style/Vars';
        header {
            width: 100%;
            height: 70px;
            background-color: $primary-color;

            #logo {
                display: flex;
                justify-content: center;
                align-items: center;
                width: 50px;
                height: 100%;
                margin-left: 20px;

                img {
                    width: 100%;
                }
            }
        }
</style>