<template>
  <div
    id="glightbox-body"
    :class="`glightbox-container nodalvideo ${
      modalOpen ? 'active' : ''
    } glightbox-clean`"
  >
    <div class="gloader visible" style="display: none"></div>
    <div class="goverlay"></div>
    <div class="gcontainer">
      <button class="gclose gbtn" @click="closeModal">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          viewBox="0 0 512 512"
          xml:space="preserve"
        >
          <g>
            <g>
              <path
                d="M505.943,6.058c-8.077-8.077-21.172-8.077-29.249,0L6.058,476.693c-8.077,8.077-8.077,21.172,0,29.249C10.096,509.982,15.39,512,20.683,512c5.293,0,10.586-2.019,14.625-6.059L505.943,35.306C514.019,27.23,514.019,14.135,505.943,6.058z"
              ></path>
            </g>
          </g>
          <g>
            <g>
              <path
                d="M505.942,476.694L35.306,6.059c-8.076-8.077-21.172-8.077-29.248,0c-8.077,8.076-8.077,21.171,0,29.248l470.636,470.636c4.038,4.039,9.332,6.058,14.625,6.058c5.293,0,10.587-2.019,14.624-6.057C514.018,497.866,514.018,484.771,505.942,476.694z"
              ></path>
            </g>
          </g>
        </svg>
      </button>
      <div class="videoContainer">
        <CommonVideoPlayer
          :options="{
            autoplay: true,
            controls: true,
            sources: [
              {
                src: '/assets/media/movie.mp4',
                type: 'video/mp4',
              },
            ],
          }"
        />
        <!-- Component for video player  from omponents>common>Videoplayer -->
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps(["modalOpen"]);
const emits = defineEmits(["modalClose"]);
const closeModal = () => {
  emits("modalClose");
};
</script>

<style lang="scss" scoped>
.nodalvideo {
  visibility: hidden;
  opacity: 0;
  transition: 0.5s;
}
.active {
  visibility: visible;
  opacity: 1;
}

.videoContainer {
  width: 92%;
  max-width: 1000px;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto auto;
}
</style>
