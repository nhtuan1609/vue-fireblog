<template>
  <div class="home">
    <div class="container">
      <BlogPost :post="welcomeScreen" />
      <BlogPost
        v-for="(post, index) in simpleBlogPosts"
        :post="post"
        :key="index"
      />
    </div>
    <div class="blog-card-wrap">
      <div class="container">
        <h3>View More Recent Blogs</h3>
        <div class="blog-cards">
          <BlogCard
            v-for="(card, index) in simpleBlogCards"
            :card="card"
            :key="index"
          />
        </div>
      </div>
    </div>
    <div class="updates">
      <div class="container">
        <h2>never miss a post. Register for your free account today!</h2>
        <router-link class="router-button" to="#">
          Register for FireBlogs <Arrow class="arrow arrow-light" />
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
import Arrow from "@/assets/Icons/arrow-right-light.svg";
import BlogPost from "@/components/BlogPost.vue";
import BlogCard from "@/components/BlogCard.vue";

export default {
  name: "Home",
  components: { Arrow, BlogPost, BlogCard },
  data() {
    return {
      welcomeScreen: {
        title: "Welcome!",
        blogPost:
          "Weekly blog articles with all things programming including HTML, CSS, JavaScript and more. Register today to never miss a post!",
        welcomeScreen: true,
        photo: "coding",
      },
      simpleBlogPosts: [
        {
          title: "This is a Filter Title 1!",
          blogHTML: "This is a filter blog post title!",
          blogCoverPhoto: "beautiful-stories",
        },
        {
          title: "This is a Filter Title 2!",
          blogHTML: "This is a filter blog post title!",
          blogCoverPhoto: "designed-for-everyone",
        },
      ],
      simpleBlogCards: [
        {
          title:
            "Blog Card #1 000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
          blogCoverPhoto: "stock-1",
          blogDate: "Jul 1, 2021",
        },
        {
          title: "Blog Card #2",
          blogCoverPhoto: "stock-2",
          blogDate: "Jul 1, 2021",
        },
        {
          title: "Blog Card #3",
          blogCoverPhoto: "stock-3",
          blogDate: "Jul 1, 2021",
        },
        {
          title: "Blog Card #4",
          blogCoverPhoto: "stock-4",
          blogDate: "Jul 1, 2021",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.home {
  margin-top: 80px;

  .blog-card-wrap {
    h3 {
      font-weight: 300;
      font-size: 28px;
      margin-bottom: 32px;
    }
  }

  .updates {
    .container {
      padding: 100px 25px;
      display: flex;
      flex-direction: column;
      align-items: center;
      @media (min-width: 800px) {
        padding: 125px 25px;
        flex-direction: row;
      }
      .router-button {
        display: flex;
        font-size: 14px;
        text-decoration: none;
        @media (min-width: 800px) {
          margin-left: auto;
        }
      }
      h2 {
        font-weight: 300;
        font-size: 32px;
        max-width: 425px;
        width: 100%;
        text-align: center;
        text-transform: uppercase;
        @media (min-width: 800px) {
          text-align: initial;
          font-size: 40px;
        }
      }
    }
  }
}
</style>
