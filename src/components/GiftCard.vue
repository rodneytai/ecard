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
                        <!-- <iframe style="width: 100%; height: 50vh;" v-bind:src="[videoURL]" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen='true' webkitallowfullscreen='true' mozallowfullscreen='true'></iframe> -->
                        <video-player  
                            class="video-player-box"
                            ref="videoPlayer"
                            :options="playerOptions"
                            :playsinline="true"
                            customEventName="customstatechangedeventname"

                            @play="onPlayerPlay($event)"
                            @pause="onPlayerPause($event)"
                            @ended="onPlayerEnded($event)"
                            @waiting="onPlayerWaiting($event)"
                            @playing="onPlayerPlaying($event)"
                            @loadeddata="onPlayerLoadeddata($event)"
                            @timeupdate="onPlayerTimeupdate($event)"
                            @canplay="onPlayerCanplay($event)"
                            @canplaythrough="onPlayerCanplaythrough($event)"

                            @statechanged="playerStateChanged($event)"
                            @ready="playerReadied">
                        </video-player>
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
import 'video.js/dist/video-js.css'
import { videoPlayer} from 'vue-video-player'

export default{
    name: 'GiftCard',
    components:{
        videoPlayer,
    },
    data(){
        return{
            gifter: "花蓮縣 徐縣長",
            greetings: "這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,這是賀詞,",
            // videoURL: "https://www.youtube.com/embed/LW7AUyUsHUo",
            playerOptions: {
                // videojs options
                muted: false,
                language: 'en',
                playbackRates: [0.5, 0.7, 1.0, 1.5, 2.0],
                sources: 
                [{
                    type: "video/mp4",
                    src: "https://cdn.theguardian.tv/webM/2015/07/20/150716YesMen_synd_768k_vp8.webm"
                }],
                poster: "/static/images/author.jpg",
            }
        }
    },
    mounted() {
        console.log('this is current player instance object', this.player)
    },
    computed: {
        player() {
            return this.$refs.videoPlayer.player
        }
    },
    methods: {
        // listen event
        onPlayerPlay(player) {
          console.log('player play!', player)
        },
        onPlayerPause(player) {
          console.log('player pause!', player)
        },
        // ...player event

        // or listen state event
        playerStateChanged(playerCurrentState) {
          console.log('player current update state', playerCurrentState)
        },

        // player is ready
        playerReadied(player) {
          console.log('the player is readied', player)
          // you can use it to do something...
          // player.[methods]
        },
        onPlayerLoadeddata(data){
            console.log('onPlayerLoadeddata',data)
        },
        onPlayerCanplay(data){
            console.log('onPlayerCanplay',data)
        },
        onPlayerCanplaythrough(data){
            console.log('onPlayerCanplaythrough',data)
        },
        onPlayerTimeupdate(){
            // console.log('onPlayerTimeupdate', data)
        },
        onPlayerPlaying(data){
            console.log('onPlayerPlaying', data)
        },
        onPlayerWaiting(data){
            console.log('onPlayerWaiting', data)
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