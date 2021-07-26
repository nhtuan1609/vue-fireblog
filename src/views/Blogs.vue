<template>
  <div class="home">
    <div class="container blog-card-wrap">
      <div class="toggle-edit">
        <span>Toggle Editing Post</span>
        <input type="checkbox" v-model="editPost" />
      </div>
      <div class="blog-cards">
        <BlogCard
          v-for="(card, index) in simpleBlogCards"
          :card="card"
          :key="index"
        />
      </div>
    </div>
  </div>
</template>

<script>
import BlogCard from "@/components/BlogCard.vue";

export default {
  name: "Home",
  components: { BlogCard },
  data() {
    return {
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
      editPost: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.home {
  margin-top: 80px;

  .blog-card-wrap {
    position: relative;
    .toggle-edit {
      display: flex;
      align-items: center;
      position: absolute;
      top: 32px;
      right: 16px;
      span {
        margin-right: 16px;
      }
      input[type="checkbox"] {
        position: relative;
        border: none;
        -webkit-appearance: none;
        background: #fff;
        outline: none;
        width: 80px;
        height: 30px;
        border-radius: 20px;
        box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
          0 2px 4px -1px rgba(0, 0, 0, 0.06);
      }
      input[type="checkbox"]:before {
        content: "";
        position: absolute;
        width: 30px;
        height: 30px;
        border-radius: 20px;
        top: 0;
        left: 0;
        background: #303030;
        transform: scale(1.1);
        transition: 750ms ease all;
        box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
          0 2px 4px -1px rgba(0, 0, 0, 0.06);
      }
      input:checked[type="checkbox"]:before {
        background: #fff;
        left: 52px;
      }
    }
  }
}
</style>
