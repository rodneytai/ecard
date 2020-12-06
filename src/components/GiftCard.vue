<template>
    <div class="container selfpos z-depth-5 border">
        <div class="row inner-cutout">
            <div class="col s12 m12 l12 xl12 "> <!-- RWD class-->
                <div >
                    <div class="gifterSec">
                        <!-- 送禮者 -->
                        <span class="">來自: {{ gifter }} 的祝福</span>
                    </div>
                    <div class="z-depth-3">
                        <!-- VIDEO from URL -->
                        <iframe style="width: 100%; height: 50vh;" v-bind:src="[videoURL]" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen='true' webkitallowfullscreen='true' mozallowfullscreen='true'></iframe>
                    </div>
                    <div class="greetingsSec z-depth-3">
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
/*For border animation to work*/
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
/*Centering the whole div*/
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
/*Background Colour Animation*/
.border{
    padding: 5px;
    background: linear-gradient(110deg, #ffeead 33%, rgba(0, 0, 0, 0) 33%), linear-gradient(110deg, #C5E7D7 34%, #88d8b0 34%);
    background-size: 400% 400%;
    background-position: 25% 50%;
    -webkit-animation: Gradient 10s ease infinite;
    -moz-animation: Gradient 5s ease infinite;
}
/*Inner BG Colour*/
.inner-cutout{
    display: block;
    background-color:#ff6f69;    
    margin: 2%;
    padding-bottom: 20px;
    background: radial-gradient(circle at top, #FF5F6D, #FFC371);
    background-size: 100%;
    background-position: 50% 50%;
}
/*Font setting for gifter and greetings*/
.gifterSec, .greetingsSec{
    text-align: center;
    font-weight: bold;
    font-family: "DFKai-SB", "BiauKai", "Microsoft JhengHei", Arial, serif 
}
.gifterSec{
    margin-top: 20px;
    margin-bottom: 20px;
    font-size: xx-large;
    color: white;
    text-shadow: 3px 3px 4px #db0000 ;
}
.greetingsSec{
    font-size: large;
    color: white;    
    background: linear-gradient(to left, #FF5F6D, #ff6f69);
    background-size: 300%;
    text-shadow: 1px 1px 3px red;
}
p{
    word-wrap: break-word;
}
</style>