<template>
  <div class="grid">
    <h2>Detalle</h2>
    <!-- <div v-if="members">
      <article class="grid product-container card">
        <div class="image">
          <img :src="`${members.avatar_url}`" alt="" />
        </div>
        <div class="product-container__content">
          <h2>
            {{ members.id }}
          </h2>
          <p>
            <span class="grey-text">Login: </span>
            <strong>{{ members.login }}</strong>
          </p>
          <p>
            <span class="grey-text">node_id: </span>
            {{ members.node_id }}
          </p>
          <p><span class="grey-text">type: </span>{{ members.type }}</p>
          <router-link :to="`/`">
          <v-btn
            color="grey"
            plain text variant="outlined">
            <v-icon
              dark
              left
            >
              mdi-arrow-left
            </v-icon>Home
          </v-btn>
            </router-link>
        </div>
        <div class="flex product-container__aside">
          <div class="text-align-end aside__price">
            {{ members.login }}
          </div>
        </div>
      </article>
    </div>
    <hr /> -->
     <v-card
      class="mx-auto"
      max-width="640"
    >
      <v-card-text>
        <div class="image">
          <img :src="`${members.avatar_url}`" alt="" />
        </div>
        <div>{{ members.id }}</div>
        <p class="text-h6">
          <span class="grey-text">Login: </span>
          <strong>{{ members.login }}</strong>
        </p>
        <p class="text-h6">
          <span class="grey-text">node_id: </span>
            {{ members.node_id }}
        </p>
        <p class="text-h6">
          <span class="grey-text">type: </span>
          {{ members.type }}
        </p>

      </v-card-text>
      <v-card-actions>

      <router-link :to="`/`">
          <v-btn
            color="grey"
            plain text variant="outlined">
            <v-icon
              dark
              left
            >
              mdi-arrow-left
            </v-icon>Home
          </v-btn>
            </router-link>
      </v-card-actions>
  
    </v-card>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Members } from "@/types";
import { memberService } from "@/services/members";

export default defineComponent({
  data: () => ({
    members: {} as Members,
  }),
  computed: {
    id(): number {
      return Number(this.$route.params.id);
    },
  },
  created() {
    console.log(this.$route.params.id);
    memberService(String(this.$route.params.id)).then(
      (members: Members | undefined) => {
        if (members) {
          this.members = members;
        }
      }
    );
  },
});
</script>
<style lang="scss" scoped>
.v-card-text {
      display: flex;
    flex-direction: column;
    align-content: center;
    align-items: center;
    opacity: 1;
}
hr {
  width: 100%;
}
h2 {
  display: flex;
    justify-content: center;
    padding: 0 0 20px 0;
}
a {
  text-decoration: none;
}
.product-list {
  padding: 0;
  li {
    margin-bottom: 2em;
  }
}
.product-container {
  align-items: flex-start;
  grid-template-columns: 210px 1fr 100px;
}
.image {
  width: 200px;
  img {
    width: 100%;
  }
}
</style>
