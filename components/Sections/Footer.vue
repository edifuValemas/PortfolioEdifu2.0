<template>
  <footer>
    <div class="footer__info">
      <div class="container footer__info-container">
        <div class="footer__copyright">
          © {{ year }} — <span v-html="$t('footer.credits')"/>
        </div>
        <a href="#top" class="footer__top-page">
          ^
        </a>
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  computed: {
    year () {
      return new Date().getFullYear()
    }
  }
}
</script>

<style lang="vss">
.footer__info {
  background-color: red;
  padding: 1.5em 0;
}
.footer__info-container {
  display: flex;
  justify-content: space-between;
  width: 100%;
  flex-direction: column;
}
@media (min-width: 400px) {
  .footer__info-container {
    flex-direction: row;
  }
}
.footer__copyright {
  text-align: center;
}
@media (min-width: 400px) {
  .footer__copyright {
    text-align: inherit;
  }
}
.footer__top-page {
  color: black;
  display: block;
  text-align: center;
  line-height: 1;
  -webkit-transition: 1s;
  -moz-transition: 1s;
  transition: 1s;
}
@media (min-width: 400px) {
  .footer__top-page {
    text-align: right;
  }
}
</style>

