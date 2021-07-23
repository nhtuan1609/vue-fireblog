<template>
  <div class="home">
    <div class="container">
      <BlogPost :post="welcomeScreen" />
      <BlogPost
        v-for="(post, index) in simpleBlogPost"
        :post="post"
        :key="index"
      />
    </div>
  </div>
</template>

<script>
import BlogPost from "@/components/BlogPost.vue";

export default {
  name: "Home",
  components: { BlogPost },
  data() {
    return {
      welcomeScreen: {
        title: "Welcome!",
        blogPost:
          "Weekly blog articles with all things programming including HTML, CSS, JavaScript and more. Register today to never miss a post!",
        welcomeScreen: true,
        photo: "coding",
      },
      simpleBlogPost: [
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
    };
  },
};
</script>

<style lang="scss" scoped>
.home {
  margin-top: 80px;
}
</style>
