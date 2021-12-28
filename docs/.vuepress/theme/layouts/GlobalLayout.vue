<template>
  <div id="global-layout">
    <header>
      <div class="wrapper">
        <a class="home-link" href="/">Zhao Yuchun</a>
        <a class="about" href="/about">About</a>
      </div>
    </header>
    <div class="content">
      <component :is="layout"/>
    </div>
    <footer class="global">
      <div style="text-align: center;">
        Made with ❤️  in Wuhan · © 2021
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  computed: {
    layout () {
      if (!this.$page.path) return 'NotFound';
      // 你也可以像默认的 globalLayout 一样首先检测 layout 是否存在
      if (!this.$frontmatter.layout) return 'Layout';
      return this.$frontmatter.layout;
    }
  }
}
</script>

<style>
#global-layout {
  height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  font-family: Georgia, STSong, serif;
}

header {
  border-top: 5px solid #424242;
  border-bottom: 1px solid #e8e8e8;
  min-height: 55.95px;
  position: relative;
}

.wrapper {
  max-width: calc(800px - (30px * 2));
  margin-right: auto;
  margin-left: auto;
  padding-right: 30px;
  padding-left: 30px;
}
.wrapper a{
  color: #424242;
  font-size: 26px;
    font-weight: 400;
    line-height: 54px;
    letter-spacing: -1px;
    margin-bottom: 0;
    float: left;
    text-decoration: none;
}

.about {
  float: right !important;
  font-size: 20px !important;
  line-height: 1.5;
  font-weight: 400 !important;
}

.wrapper a:hover {
  text-decoration: underline;
}

footer.global {
  padding: 15px 0;
  border-top: 1px solid #e8e8e8;
}

.content {
  flex: 1;
}
</style>