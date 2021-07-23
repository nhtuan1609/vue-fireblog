<template>
  <div class="card-wrapper">
    <div class="icon-wrapper">
      <Edit class="icon" />
      <Delete class="icon" />
    </div>
    <div class="card-photo">
      <img
        :src="require(`@/assets/blogCards/${card.blogCoverPhoto}.jpg`)"
        :alt="card.blogCoverPhoto"
      />
    </div>
    <div class="card-content">
      <div>
        <h2 class="card-title">{{ card.title }}</h2>
        <p class="card-date">Posted on: {{ card.blogDate }}</p>
      </div>
      <router-link class="link" to="#">
        VIEW THE POST<Arrows class="arrow" />
      </router-link>
    </div>
  </div>
</template>

<script>
import Arrows from "@/assets/Icons/arrow-right-light.svg";
import Edit from "../assets/Icons/edit-regular.svg";
import Delete from "../assets/Icons/trash-regular.svg";

export default {
  name: "BlogCard",
  props: ["card"],
  components: { Arrows, Edit, Delete },
};
</script>

<style lang="scss" scoped>
.card-wrapper {
  position: relative;
  display: flex;
  flex-direction: column;
  width: 300px;
  height: 400px;
  overflow: hidden;
  border-radius: 4px;
  transition: 0.5s ease all;
  &:hover {
    transform: rotateZ(-1deg) scale(1.01);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
      0 2px 4px -1px rgba(0, 0, 0, 0.06);
  }

  .icon-wrapper {
    position: absolute;
    top: 8px;
    right: 8px;
    display: flex;
    gap: 8px;

    .icon {
      width: 34px;
      height: 34px;
      font-size: 2px;
      padding: 10px;
      border-radius: 50%;
      background-color: #fff;

      &:hover {
        cursor: pointer;
        background-color: rgb(204, 204, 204);
      }
    }
  }

  .card-photo {
    height: 50%;
    img {
      display: block;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  .card-content {
    height: 50%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    background-color: #fff;
    div {
      flex: 1;
      width: 100%;
      padding: 0 16px;
      padding-top: 32px;
      .card-title {
        font-size: 18px;
        font-weight: 400;
        overflow: hidden;
        text-overflow: ellipsis;
      }
      .card-date {
        font-size: 12px;
        font-weight: 400;
        margin: 10px 0;
      }
    }

    .link {
      display: inline-flex;
      align-items: center;
      margin: 32px 16px;
      padding-bottom: 4px;
      border-bottom: 1px solid transparent;
      font-size: 12px;
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
</style>
