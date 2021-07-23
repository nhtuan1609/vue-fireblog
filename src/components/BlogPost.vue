<template>
  <div class="blog-wrapper">
    <div class="blog-content">
      <div>
        <h2 v-if="post.welcomeScreen">{{ post.title }}</h2>
        <h2 v-else>{{ post.title }}</h2>
        <p v-if="post.welcomeScreen">{{ post.blogPost }}</p>
        <p v-else class="content-preview">{{ post.blogHTML }}</p>
        <router-link v-if="post.welcomeScreen" class="link link-light" to="#">
          Login/Register<arrows class="arrow arrow-light" />
        </router-link>
        <router-link v-else class="link" to="#">
          View The Post<Arrows class="arrow" />
        </router-link>
      </div>
    </div>
    <div class="blog-photo">
      <img
        v-if="post.welcomeScreen"
        :src="require(`@/assets/blogPhotos/${post.photo}.jpg`)"
        :alt="post.photo"
      />
      <img
        v-else
        :src="require(`@/assets/blogPhotos/${post.blogCoverPhoto}.jpg`)"
        :alt="post.blogCoverPhoto"
      />
    </div>
  </div>
</template>

<script>
import Arrows from "@/assets/Icons/arrow-right-light.svg";

export default {
  name: "BlogPost",
  props: ["post"],
  components: { Arrows },
};
</script>

<style lang="scss" scoped>
.blog-wrapper {
  display: flex;
  flex-direction: row;
  height: 650px;
  margin: 10px;
  overflow: hidden;
  border-radius: 4px;
  box-shadow: 0px 0px 6px 1px rgba(0, 0, 0, 0.3);
  @media (max-width: 800px) {
    flex-direction: column;
    height: auto;
  }
  .blog-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 3;
    order: 1;
    @media (max-width: 800px) {
      flex: 4;
      order: 2;
    }
    div {
      max-width: 375px;
      padding: 72px 24px;
      @media (min-width: 800px) {
        padding: 0 24px;
      }
      h2 {
        font-size: 32px;
        font-weight: 300;
        text-transform: uppercase;
        margin-bottom: 24px;
        @media (min-width: 800px) {
          font-size: 40px;
        }
      }
      p {
        font-size: 16px;
        font-weight: 300;
        line-height: 1.7;
      }
      .content-preview {
        font-size: 16px;
        max-height: 24px;
        width: 250px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
      }
      .link {
        display: inline-flex;
        align-items: center;
        margin-top: 32px;
        padding-bottom: 4px;
        border-bottom: 1px solid transparent;
        transition: 0.5s ease-in all;
        &:hover {
          border-bottom-color: #303030;
        }
      }
      .link-light {
        &:hover {
          border-bottom-color: #ffff;
        }
      }
    }
  }

  .blog-photo {
    flex: 4;
    order: 2;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
      0 2px 4px -1px rgba(0, 0, 0, 0.06);
    @media (max-width: 800px) {
      flex: 3;
      order: 1;
    }
    img {
      display: block;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &:nth-child(even) {
    .blog-content {
      order: 2;
    }
    .blog-photo {
      order: 1;
    }
  }
}
</style>
