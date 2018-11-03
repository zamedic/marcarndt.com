<template>
<div>
    <div v-for="(post,index) in posts"
         :key="post.slug + '_' + index">
        <v-card class="my-3" hover>
            <v-card-media
                    class="white--text"
                    height="170px"
                    :src="post.featured_image"
            >
                <v-container fill-height fluid>
                    <v-layout>
                        <v-flex xs12 align-end d-flex>
                            <span class="headline">{{ post.title }}</span>
                        </v-flex>
                    </v-layout>
                </v-container>
            </v-card-media>
            <v-card-text>
                {{ post.summary }}
            </v-card-text>
            <v-card-actions>
                <v-btn icon class="red--text">
                    <v-icon medium>fa-reddit</v-icon>
                </v-btn>
                <v-btn icon class="light-blue--text">
                    <v-icon medium>fa-twitter</v-icon>
                </v-btn>
                <v-btn icon class="blue--text text--darken-4">
                    <v-icon medium>fa-facebook</v-icon>
                </v-btn>
                <v-spacer></v-spacer>
                <router-link :to="'/blog/' + post.slug">
                    <v-btn flat class="blue--text">Read More</v-btn>
                </router-link>
            </v-card-actions>
        </v-card>
    </div>
</div>

</template>

<script>
import { butter } from "../butter.js";

export default {
  data() {
    return {
      title: "Your Logo",
      posts: []
    };
  },
  methods: {
    getPosts() {
      butter.post
        .list({
          page: 1,
          page_size: 10
        })
        .then(res => {
          this.posts = res.data.data;
        });
    }
  },
  created() {
    this.getPosts();
  }
};
</script>
