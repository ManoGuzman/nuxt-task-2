 <!-- pages/sports_index.vue -->
<template>
  <div class="container">
   <HeaderView />
   <h3 style="margin-top: 15px">Noticias Deportes</h3>
   <p>Las últimas noticias sobre deportes a nivel nacional.</p>
   <ul>
     <ContentList path="/sports" v-slot="{ list }">
        <li v-for="sports in list" :key="sports._path">
         <NuxtLink :to="sports._path">{{ sports.title }}</NuxtLink>
        </li>
      </ContentList>
   </ul>
  <FooterView />
 </div>
</template>