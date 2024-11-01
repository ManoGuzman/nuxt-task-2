<!-- pages/lifestyle_index.vue -->
<template>
  <div class="container">
    <HeaderView />
    <h3 style="margin-top: 15px">Noticias Estilo Vida</h3>
    <p>Las últimas noticias sobre el estilo de vida.</p>
    <ul>
      <ContentList path="/lifestyle" v-slot="{ list }">
        <li v-for="lifestyle in list" :key="lifestyle._path">
          <NuxtLink :to="lifestyle._path">{{ lifestyle.title }}</NuxtLink>
        </li>
      </ContentList>
    </ul>
    <FooterView />
  </div>
</template>
