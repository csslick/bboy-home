<script>
  // news 데이터 가져오는 함수
  import { getNews } from '../../assets/news';

  // params 가져오기(props로 전달)
  export let params = {};
  console.log(params);
  console.log(getNews(Number(params.id)));
  let news = getNews(Number(params.id));

</script>

<main class="container">
  <div class="main-header">
    <h2>{news.title}</h2>
    <p class="date">{news.date}</p>
    <img src={news.detailImgUrl} alt={news.title}>
  </div>
  <article>
    {@html news.desc}
  </article>
</main>

<style lang="scss">
  .main-header {
    h2 { margin-bottom: 10px; }
    .date { 
      margin-bottom: 20px; 
      font-size: 15px;
      color: #666;
    }
  }
  article { margin-top: 50px; }

  .container {
    background: #fff;
  }

  @media (max-width: 516px) {
    .container {
      padding: 20px;
    }
   .main-header {
      img {
        width: 100%;
      }
    }
  } 
</style>