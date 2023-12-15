<template>
    <body>
        <div id="display-content">
            <h1>Usuario</h1>
            <img :src="perfil" alt="user-icon">
            <span>Nombre: </span><b id="name">{{ name }}</b>
            <hr>
            <span>Mail: </span><b id="mail">{{ mail }}</b>
            <hr>
            <span>Intereses: </span><b id="interest">{{ intereses }}</b>
            <hr>
            <button @click="handleEditProfile">Editar Perfil</button>
        </div>
        <div id="edit-content">
            <h1>Usuario</h1>
            <img :src="perfil" alt="user-icon">
            <span>Nombre: </span>
            <input type="text" id="input-name" v-model="name"/>
            <hr>
            <span>Mail: </span>
            <input type="text" id="input-mail" v-model="mail"/>
            <hr>
            <span>Intereses: </span>
            <input type="text" id="input-interest" v-model="intereses"/>
            <hr>
            <button @click="handleUpdateProfile">Guardar Perfil</button>
        </div>
    </body>
</template>

<script>
    import fotito from '../public/assets/profile.png'
    export default{
        name: 'App', 
        data(){
            return {
                perfil: fotito,
                name: "Nombre uno",
                mail: "nombre@ejemplo.com",
                intereses: "Messi",
                }
            },
        methods: {
            handleEditProfile(){
                document.getElementById("display-content").style.display = 'None'
                document.getElementById("edit-content").style.display = 'Block'
            },
            handleUpdateProfile(){
                document.getElementById("display-content").style.display = 'Block'
                document.getElementById("edit-content").style.display = 'None'
            }
        }
        }


</script>

<style>
img {
    width: 320px;
    height: 270px;
    display: block;
    margin-bottom: 40px;
}

#display-content{
    margin: 30px auto;
    width: 80%;
}

#edit-content {
    margin: 30px auto;
    width: 80%;
    display: none;
}

hr {
    width: 400px;
    margin: 25px 0;
}

button {
    width: 160px;
    height: 45px;
    border-radius: 5px;
    font-size: 15px;
}

button:hover {
    cursor: pointer;
}

input {
    width: 200px;
    font-size: 15px;
    padding: 10px;
}

</style>