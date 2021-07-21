<template>
  <vue-jitsi-meet
    ref="jitsiRef"
    domain="meet.jit.si"
    :options="jitsiOptions"
  ></vue-jitsi-meet>
</template>

<script>
import { JitsiMeet } from "@mycure/vue-jitsi-meet";
export default {
  components: {
    VueJitsiMeet: JitsiMeet,
  },
  computed: {
    jitsiOptions() {
      return {
        roomName: this.$route.query.roomName,
        width: "100%",
        height: "100%",
        noSSL: false,
        userInfo: {
          email: this.$route.query.email,
          displayName: this.$route.query.displayName,
        },
        configOverwrite: {
          enableNoisyMicDetection: false,
        },
        interfaceConfigOverwrite: {
          SHOW_JITSI_WATERMARK: false,
          SHOW_WATERMARK_FOR_GUESTS: false,
          SHOW_CHROME_EXTENSION_BANNER: false,
        },
        onload: this.onIFrameLoad,
      };
    },
  },
  mounted: function () {
    console.log(this.$route.query);
  },
  methods: {
    onIFrameLoad() {
      // do stuff
    },
  },
};
</script>

<style scoped>
.wrap {
  margin-bottom: -10;
}
.watermark {
  display: none;
}
</style>
