<script setup lang="ts">
import { onMounted } from 'vue';

// 등록된 링크 목록을 정의합니다. (인자값: 이동할 링크)
const links: Record<string, string> = {
  mail: "mailto:me@hyunsang.dev",
  ig: 'https://instagram.com/p._.hyunsang',
  gh: 'https://github.com/dev-hyunsang',
  blog: 'https://blog.hyunsang.dev',
  news: 'https://news.hyunsang.dev',
  resume: 'https://hyunsang.dev',
  li: 'https://linkedin.com/in/parkhyunsang',
  til: 'https://til.hyunsang.dev'
};

onMounted(() => {
  const path = window.location.pathname.replace(/^\/+|\/+$/g, '');
  
  if (path && links[path]) {
    window.location.href = links[path];
  } else if (path) {
    window.location.href = '/';
  }
});
</script>

<template>
  <div id="app" class="main-container">
    <h1 class="title">HyunSang Park</h1>
    <div class="btn-container">
      <button class="link-btn">
        <a href="/mail">Send Mail <span class="parameter">/mail</span> &rarr;</a>
      </button>
      <button class="link-btn">
        <a href="/resume">Resume <span class="parameter">/resume</span> &rarr;</a>
      </button>
      <button class="link-btn">
        <a href="/blog">Blog <span class="parameter">/blog</span> &rarr;</a>
      </button>
      <button class="link-btn">
        <a href="/til">TIL <span class="parameter">/til</span> &rarr;</a>
      </button>
      <button class="link-btn">
        <a href="/news">News <span class="parameter">/news</span> &rarr;</a>
      </button>
      <button class="link-btn">
        <a href="/gh">GitHub <span class="parameter">/gh</span> &rarr;</a>
      </button>
      <button class="link-btn">
        <a href="/li">Linkedin <span class="parameter">/li</span> &rarr;</a>
      </button>
      <button class="link-btn">
        <a href="/ig">Instagram <span class="parameter">/ig</span> &rarr;</a>
      </button>
    </div>
  </div>
</template>

<style scoped>
.main-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  font-family: 'Menlo', 'Monaco', 'Courier New', monospace;
}
a, p, h1, span {
  color: #fff;
}
button, a {
  text-decoration: none;
  cursor: pointer;
}
.title {
  font-size: 3rem;
}
.parameter {
  font-size: 0.8rem;
  color: #ccc;  
}
.btn-container {
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  max-width: 800px;
  margin-top: 1rem;
  display: flex;
} 
.link-btn {
  font-size: 1rem;
  margin: 1rem;
  padding: 1rem;
  border-radius: 5px;
  border: 1px solid #ccc;
  cursor: pointer;
  background-color: #000;
}
.link-btn:hover {
  background-color: #ccc;
  color: #000;
}
</style>