<template lang="html">
  <div
    v-lazy-container="{ selector: 'img' }"
    :class="`image-placeholder ${isRounded}`"
  >
    <img
      :data-src="imageRequired"
      :data-loading="imageRequired.placeholder"
      :width="width"
      :height="height"
      :class="classes"
      :alt="alt"
    />
  </div>
</template>

<script>  
export default {
  props: {
    imageURL: {
      type: String
    },
    alt: {
      type: String
    },
    width: {
      type: String
    },
    height: {
      type: String
    },
    classes: {
      type: String
    },
    alt: {
      type: String
    },
    rounded: {
      type: Boolean,
      default: false
    }
  },
  computed: {
    imageRequired() {
      return require(`../assets/images/${this.imageURL}`)
    },
    isRounded() {
      return this.rounded ? 'image-placeholder--rounded' : ''
    }
  }
}
</script>

<style scoped lang="css">
.image-placeholder {
  overflow: hidden;
  line-height: 0;
}
.image-placeholder--rounded {
  border-radius: 100%;
}

img {
  transition: all ease 0.3s;
  opacity: 0;
}
img[lazy=loading] {
  opacity: 1;
  filter: blur(15px);
}
img[lazy=loaded] {
  opacity: 1;
}
</style>
