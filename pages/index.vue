<!-- pages/index.vue -->
<template>
 <div class="container">
   <HeaderView />
   <h2 style="margin-top: 15px">NOTICIAS MD</h2>
    <p>Noticiero digital sobre noticias nacional sobre sucesos, deportes y variedad.</p>
    <ul>
      <li> <NuxtLink to="/news_index">NOTICIAS NACIONALES</NuxtLink></li>
      <li> <NuxtLink to="/sports_index">NOTICIAS DEPORTES</NuxtLink></li>
      <li> <NuxtLink to="/lifestyle_index">NOTICIAS DE VARIEDAD</NuxtLink></li>
    </ul>
   <FooterView />
 </div>
</template>

<script>
export default {
  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
};
</script>