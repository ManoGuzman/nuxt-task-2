 <!-- pages/news_index.vue -->
<template>
  <div class="container">
   <HeaderView />
   <h3 style="margin-top: 15px">Noticias Nacionales</h3>
     <p>Las últimas noticias sobre el ámbito nacional.</p>
   <ul>
     <ContentList path="/news" v-slot="{ list }">
        <li v-for="news in list" :key="news._path">
         <NuxtLink :to="news._path">{{ news.title }}</NuxtLink>
        </li>
      </ContentList>
   </ul>
   <FooterView />
 </div>
</template>
