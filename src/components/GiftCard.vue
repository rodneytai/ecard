<template>
    <div class="container selfpos z-depth-5 lime lighten-5 border">
        <div class="row inner-cutout">
            <div class="col s12 m12 l12 xl12 "> <!-- RWD class-->
                <div class="">
                    <div class="gifterSec knockout">
                        <!-- 送禮者 -->
                        <span class="">來自: {{ gifter }} 的祝福</span>
                    </div>
                    <div class="z-depth-3">
                        <!-- VIDEO from URL -->
                        <iframe style="width: 100%; height: 50vh;" v-bind:src="[videoURL]" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen='true' webkitallowfullscreen='true' mozallowfullscreen='true'></iframe>
                    </div>
                    <div class="card-content greetingsSec z-depth-2">
                        <!-- 賀詞/祝福語 -->
                        <p>{{ greetings }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default{
    name: 'GiftCard',
    data(){
        return{
            gifter: "花蓮縣長 X縣長",
            greetings: "這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,",
            videoURL: "https://www.youtube.com/embed/LW7AUyUsHUo",
        }
    },
}
</script>

<style scoped>
@-webkit-keyframes Gradient {
    0% {
        background-position: 30% 50%
    }
    50% {
        background-position: 25% 50%
    }
    100% {
        background-position: 30% 50%
    }
    
}
div .selfpos{
    /*position: absolute;*/
    /*top: 50%;*/
    /*left: 50%;*/
    /*width: 100%;*/
    /*height: 70%;*/
    /*-webkit-transform: translate(-50%, -50%);*/
    /*transform: translate(-50%, -50%);*/
    position: relative;
    display: flex;
    justify-content: center;
    margin-top: 3%;    
}
.border{
    padding: 5px;
    background: linear-gradient(110deg, #ffeead 33%, rgba(0, 0, 0, 0) 33%), linear-gradient(110deg, #C5E7D7 34%, #88d8b0 34%);
    background-size: 400% 400%;
    /*height: 400px;*/
    background-position: 25% 50%;
    -webkit-animation: Gradient 15s ease infinite;
    -moz-animation: Gradient 5s ease infinite;
}
.inner-cutout{
    /*padding: 40px 0;*/
    display: block;
    background-color:#ff6f69;    
    margin: 2%;
    /*padding-bottom: 40px;*/
    /*height: 300px;*/
    background: radial-gradient(#ff6f69, #ff8b87);
    background-size: 300%;
    /*background-position:50% 50%;*/
}
.knockout {
    
    vertical-align: middle;
    text-align: center;
    font-family: 'Pacifico', cursive;
    font-size:50pt;
    color: blue;
    color: #fff;
    background: linear-gradient(110deg, #ffeead 33%, rgba(0, 0, 0, 0) 33%), linear-gradient(110deg, #C5E7D7 34%, #88d8b0 34%);
    background-size: 400%;
     -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;
}
.knockout{
        animation: Gradient 5s ease infinite;
        -webkit-animation: Gradient 15s ease infinite;
        -moz-animation: Gradient 5s ease infinite;
}

.gifterSec, .greetingsSec{
    text-align: center;
    font-weight: bold;
    font-family: "DFKai-SB", "BiauKai", "Microsoft JhengHei", Arial, serif 
}
.gifterSec{
    margin-top: 20px;
    margin-bottom: 20px;
    font-size: xx-large;
}
.greetingsSec{
    font-size: large;
}
p{
    word-wrap: break-word;
}
.testtt{
    background: rgb(34,193,195);
    background: linear-gradient(180deg, rgba(34,193,195,1) 0%, rgba(253,187,45,1) 100%);
}
</style>