<template>
  <div class="container">
    <h3>VueJs MediaRecorder API</h3>
    Record Video:
    <vue-record-video @result="onResultVideo" />
    <video
      width="300px"
      height="300px"
      :src="video"
      :key="index"
      controls="controls"
    />
    Record Audio:
    <vue-record-audio @result="onResultAudio" />
    <audio
      width="300px"
      height="300px"
      :src="audio"
      :key="index"
      controls="controls"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      audio: null,
      video: null,
    };
  },
  methods: {
    onResultVideo(data) {
      this.video = window.URL.createObjectURL(data);
    },
    onResultAudio(data) {
      this.audio = window.URL.createObjectURL(data);
    },
  },
};
</script>

<style lang="stylus" scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.btn {
  margin: 10px 0px;
  width: 200px;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.item {
  padding: 20px 20px;
}
</style>