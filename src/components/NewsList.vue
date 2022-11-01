<template>
  <section>
    <ul class="news-list">
      <li class="news-card" v-for="newsItem in newsList" :key="newsItem.id">
        <p><span class="heading">Title</span>: {{ newsItem.title }}</p>
        <p><span class="heading">Author</span>: {{ newsItem.author }}</p>
        <p>
          <span class="heading">Description</span>: {{ newsItem.description }}
        </p>
        <p><span class="heading">Source</span>: {{ newsItem.source.name }}</p>
      </li>
    </ul>
  </section>
</template>

<script>
import axios from "axios";
import { onMounted, ref } from "vue";

export default {
  name: "NewsList",

  setup() {
    const newsList = ref([]);

    const fetchNews = () => {
      axios
        .get(
          "https://newsapi.org/v2/everything?q=bitcoin&apiKey=94585b39692e4ea6b372bea15abf7dcc"
        )
        .then((response) => (newsList.value = response.data.articles));
    };

    onMounted(() => {
      fetchNews();
    });

    return { newsList };
  },
};
</script>

<style scoped>
ul.news-list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 3rem;
}

ul li.news-card {
  padding: 10px;
  display: flex;
  border-radius: 8px;
  flex-direction: column;
  row-gap: 5px;
  box-shadow: 0px 4px 12px -1px rgba(120,116,120,0.79);
}

li p span.heading {
  font-weight: 600;
  font-size: 18;
}
</style>
