<template>
  <div class="card text-center m-3">
    <div class="form">
      <label for="Name">Teclee nombre de la empresa:</label>
      <input type="text" v-model="corporacion" class="input" />
      <!-- {{ corporacion }} -->
      <v-btn v-on:click="changeCoportation" color="grey" plain>
        Buscamos
      </v-btn>
    </div>
    <div class="card-body">Total vue Members: {{ members.length }}</div>
    <div class="d-flex justify-space-between align-center f-wrap">
      <v-card :loading="loading" class="mx-auto my-12" max-width="250" v-for="members in members" :key="members.id">
        <template>
          <v-progress-linear
            color="deep-purple"
            height="10"
            indeterminate
          ></v-progress-linear>
        </template>
        <v-img
          :src="`${members.avatar_url}`"
          class="align-self-stretch"
          height="250"
          width="250"
          align="center"
        ></v-img>

        <v-card-title>{{ members.login }}</v-card-title>

        <v-card-text>


        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-actions>
          
          <v-btn v-on:click="redirectDetalle(members.login)"
                color="grey"
                plain text @click="reserve" variant="outlined">
            <v-icon>mdi-format-list-bulleted-square</v-icon>Ver detalle
          </v-btn>
        </v-card-actions>
      </v-card>
    </div>
    <!-- <nav>
      <div>Listado de Miembros</div>
    </nav>
    <ul class="product-list">
      <li v-for="members in members" :key="members.id">
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
            <p>
              <v-btn
                v-on:click="redirectDetalle(members.login)"
                color="grey"
                plain
              >
                Ver Detalle
              </v-btn>
            </p>
          </div>
        </article>
      </li>
    </ul> -->
    
    
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Members } from "@/types";
import { memberListService } from "@/services/members";

export default defineComponent({
  name: "get-request",
  data() {
    return {
      id: Number,
      filter: {},
      members: [] as Members[],
      search: {},
    };
  },
  // computed: {

  // },
  methods: {
    changeCoportation: function () {
      memberListService(String(this.corporacion)).then(
        (members: Members[] | undefined) => {
          if (members) {
            this.members = members;
          }
        }
      );
    },
    detalleMiembro: function (id: number, corporacion: string) {
      console.log("id de detalle", id);
      console.log("corporacion: ", corporacion);
      const search = this.members.filter((member) => member.id === id);
      this.search = search;
      this.members = search;
      console.log("he pulsado en ver detalle", id);
      this.$router.push("/detail/" + id);
    },
    redirectDetalle: function (id: number) {
      console.log("id de detalle", id);
      this.$router.push("/detail/" + id);
    },
  },
  computed: {
    corporacion: {
      get() {
        // recuperamos el valor del input
        return this.$store.getters.flavor;
      },
      set(value) {
        // seteamos el valor del imput al contexto
        this.$store.commit("change", value);
      },
    },
  },
  // ciclos de vida
  async created() {
    // Simple GET request using fetch
    console.log(
      "inicio del ciclo de vida del componente con.- " + this.corporacion
    );
  },
});
</script>
<style lang="scss" scoped>
.f-wrap {
  flex-wrap: wrap;
  margin: 20px!important;
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
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
  align-content: center;
  justify-content: flex-start;
      padding: 0 20px 20px;
    margin-bottom: 20px;
    border-bottom: 1px solid yellowgreen;
  .label {
    display: block;
    padding-bottom: 0.5rem;
  }
  .input {
    border: 1px solid lightgrey;
    border-radius: 5px;
    display: block;
    padding: 0.5rem;
    margin-bottom: 0.5rem;
  }
}
</style>
