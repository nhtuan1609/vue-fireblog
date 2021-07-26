<template>
  <footer>
    <div class="container">
      <div class="left">
        <div class="col-1">
          <router-link class="header" :to="{ name: 'Home' }">
            FireBlogs
          </router-link>
          <ul>
            <li>
              <a href="#"><instagram class="svg-icon"/></a>
            </li>
            <li>
              <a href="#"><linkedin class="svg-icon"/></a>
            </li>
            <li>
              <a href="#"><youtube class="svg-icon"/></a>
            </li>
            <li>
              <a href="#"><twitter class="svg-icon"/></a>
            </li>
          </ul>
        </div>
        <div class="col-2">
          <ul>
            <router-link class="link" :to="{ name: 'Home' }">Home</router-link>
            <router-link class="link" :to="{ name: 'Blogs' }">
              Blogs
            </router-link>
            <router-link v-if="admin" class="link" to="#"
              >Create Post</router-link
            >
            <router-link v-if="!user" class="link" to="#"
              >Login In / Register</router-link
            >
          </ul>
        </div>
      </div>
      <div class="right">
        <p>Copyright 2021 All Rights Reserved</p>
      </div>
    </div>
  </footer>
</template>

<script>
import youtube from "@/assets/Icons/youtube-brands.svg";
import twitter from "@/assets/Icons/twitter-brands.svg";
import instagram from "@/assets/Icons/instagram-brands.svg";
import linkedin from "@/assets/Icons/linkedin-brands.svg";

export default {
  name: "Footer",
  components: { youtube, twitter, instagram, linkedin },
  data() {
    return {
      admin: true,
      user: false,
    };
  },
};
</script>

<style lang="scss" scoped>
footer {
  margin-top: auto;
  padding: 100px 25px;
  background-color: #303030;
  .container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 0px;
    @media (max-width: 800px) {
      flex-direction: column;
      align-items: center;
      gap: 32px;
    }
    .left {
      flex: 1;
      display: flex;
      @media (max-width: 800px) {
        flex-direction: column;
        gap: 32px;
      }
      .col-1 {
        flex: 1;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 32px;
        @media (max-width: 800px) {
          align-items: center;
        }
        .header {
          text-decoration: none;
          font-size: 26px;
          font-weight: 500;
          color: #fff;
        }
        ul {
          display: flex;
          list-style: none;

          li {
            margin-right: 16px;
            .svg-icon {
              height: 26px;
              color: #fff;
            }
          }
          li:last-child {
            margin-right: 0;
          }
        }
      }
      .col-2 {
        flex: 1;
        ul {
          display: flex;
          flex-direction: column;
          align-items: flex-start;
          gap: 16px;
          @media (max-width: 800px) {
            flex-direction: row;
          }
          .link {
            font-size: 16px;
            font-weight: 500;
            color: #fff;
          }
        }
      }
    }
    .right {
      flex: 1;
      display: flex;
      align-items: flex-end;
      p {
        color: #fff;
        margin-left: auto;
        margin-right: 0;
      }
    }
  }
}
</style>
