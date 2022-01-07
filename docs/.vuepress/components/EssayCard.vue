<template>
  <div class="essay">
    <span class="post-meta">{{date}}</span>
    <h3>
      <a class="post-link" :href="link">{{title}}</a>
    </h3>
  </div>
</template>

<script>
export default {
  props: ["title", "date", "link"],
  methods: {
    toEssay(){
      location.href = this.link;
    }
  }
}
</script>

<style>
body {
  font: 400 16px/1.5 -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol";
}
.essay {
  margin-bottom: 30px;
  margin-top: 0 !important;
}

.essay h3 {
  margin: 0 !important;
  padding: 0!important;
}

.post-meta {
  font-size: 14px;
  color: #828282;
  font-weight: 400;
}

.post-link {
  text-decoration: none;
  color: #2a7ae2;
  font-size: 24px;
  font-weight: 700;
}

.post-link:hover{
  color: #111;
  text-decoration: underline;
}
</style>