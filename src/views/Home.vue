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
    <div class="card-container">
      <div class="container">
        <h2 class="card-list-title">View More Recent Blogs</h2>
        <div class="card-list">
          <BlogCard
            v-for="(card, index) in simpleBlogCards"
            :card="card"
            :key="index"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BlogPost from "@/components/BlogPost.vue";
import BlogCard from "@/components/BlogCard.vue";

export default {
  name: "Home",
  components: { BlogPost, BlogCard },
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

  .card-container {
    background-color: #f1f1f1;
    padding: 100px 10px;
  }

  .card-list-title {
    font-size: 24px;
    font-weight: 400;
    margin-bottom: 32px;
  }

  .card-list {
    display: flex;
    flex-wrap: wrap;
    gap: 32px;
  }
}
</style>
