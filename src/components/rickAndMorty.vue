<template>
    <div class="all">
        <img class="title" src="https://1000marcas.net/wp-content/uploads/2022/04/Rick-and-Morty.png" alt="Title" srcset="">
        <div class="container">
            <div v-for="(element, index) in charactors.results" :key="index" class="element" onclick="">
                <img class="picture" :src="element.image" alt="">
                <div class="info">
                    <h1>
                        {{element.name}}
                    </h1>
                    <p>
                        <span id="status" :class="element.status"></span> <span class="status">{{element.status}} - {{element.species}}</span> <br> <br> 
                        <span class="last"> Last Known Location: </span><br>
                        <span class="location">{{element.location.name}} </span>
                    </p>
                </div>
            </div>
        </div>
        <div class="buttons">
            <div class="prev" v-if="charactors.info.prev" @click="callingAPI(charactors.info.prev)"> ← </div>
            <div class="next" v-if="charactors.info.next" @click="callingAPI(charactors.info.next)"> → </div>
        </div>
    </div>
</template>
<script>

export default {
    name : "rickAndMorty",
    data() {
        return {
            charactors: []
        }
    },
    methods: {
        callingAPI(link) {
            fetch(link).then((res) => res.json().then(data  => {
                this.charactors = data
            })
            )
        }
    },
    mounted() {
        this.callingAPI("https://rickandmortyapi.com/api/character")
    },
}
</script>
<style>
.title{
    width: 50%;
    margin: -100px 0px;
}
.all{
    background: rgb(2,0,36);
    background: radial-gradient(circle, rgba(2,0,36,1) 0%, rgba(5,5,51,1) 100%);
}

.container{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}
.element{
    margin: 10px;
    background-color: #3C3E44;
    color: white;
    padding: 0;
    border-radius: 30px;
    display: flex;
    width: 600px;
}
.info{
    text-align: left;
    margin: 0px 10px;
}
h1{
    font-weight:normal;
    font-size: 40px;
    font-family: 'Patrick Hand', cursive;
    text-align: left;
    margin-bottom: 0;
}
h1:hover{
    color:#00B5CC;
    cursor: pointer;
}
.element:hover{
    box-shadow: 0px 0px 0px 5px #00B5CC;
    z-index: 3;
}
.picture{
    width: 40%;
    border-start-start-radius: 30px;
    border-end-start-radius: 30px;
    margin: 0;
}
.last{
    color: rgba(255, 255, 255, 0.568);
}
.status{
    font-size: large;
}
#status{
    width: 10px;
    height: 10px;
    border-radius: 50%;
    display: inline-block;
}
.Alive{
    background-color: rgb(52, 255, 1);
}
.Dead{
    background-color: red;
}
.unknown{
    background-color: rgb(255, 255, 255);
}
.buttons{
    height: 100px;
    display: flex;
    justify-content: space-around;
}
.next{
    width: 70px;
    height: 70px;
    border-radius: 50%;
    background-color: green;
    display: flex;
    color: white;
    justify-content: center;
    align-items: center;
    font-size: 40px;
}
.prev{
    width: 70px;
    height: 70px;
    border-radius: 50%;
    background-color: green;
    display: flex;
    color: white;
    justify-content: center;
    align-items: center;
    font-size: 40px;
}
</style>