<template>
 <div class="hello">
    <d-player ref="player" @play="play" :video="video" :contextmenu="contextmenu"></d-player>
  </div>
</template>

<script>
import VueDPlayer from './VueDPlayerHls';
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      video: {
          url: 'api/live/cctv1_2/index.m3u8',
          pic: 'https://www.baidu.com/img/pcpad_e247c0f9a461b6394da20e308588818f.png',
          type: 'hls'
        },
        autoplay: false,
        player: null,
        contextmenu: [
            {
                text: '百途媒资播放器',
                link: 'xxxxx'
            }
        ]
    }
  },
  components: {
    'd-player': VueDPlayer
  },
  methods: {
    play() {
        console.log('play callback')
      }
  },
  mounted() {
    this.player = this.$refs.player.dp;

    // console.log(this.player);
    // var hls = new Hls();
    // hls.loadSource('https://logos-channel.scaleengine.net/logos-channel/live/biblescreen-ad-free/chunklist_w630020335.m3u8');
    // hls.attachMedia(this.player);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
