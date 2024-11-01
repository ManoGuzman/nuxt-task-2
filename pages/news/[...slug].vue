 <!-- pages/news/[...slug].vue -->
 <script>
 export default {
   async asyncData({ $content, params }) {
     const news = await $content('news', params.slug).fetch()
     return { news }
   }
 }
</script>
 
 <template>
  <div class="container">
   <HeaderView />
   <div class="row">
		 <ContentDoc v-slot="{doc}">
     <div class="three columns">
       <img class="u-max-full-width" :src="'/images/'+doc.image">
     </div>
     <div class="six columns">
       <h4>{{doc.title}}</h4>
       Periodista: {{doc.journalist}}; Fecha: {{doc.publishDate}}; 
       Tipo de noticias: {{doc.category}}
       <pre></pre>
       <h5>Nota</h5>
       <ContentRenderer :value="doc" />
       <PrevNextNews />
     </div>
		</ContentDoc>
   </div>
   <FooterView />
 </div>
</template>