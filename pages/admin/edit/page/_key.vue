<template>
  <v-container>
    <v-layout row wrap>
      <v-flex xs12 md10 offset-md1>

        <v-progress-circular
          v-if="loading"
          indeterminate
          :size="40"
          color="amber"
        />

        <v-card v-else>
          <v-card-text>
            <!-- id: {{ page.id }}<br> -->
            <!-- key: {{ page.key }}<br> -->
            title: {{ page.title }}<br>
            slug: {{ page.slug }}
            <!-- <h1>Create Page</h1>
            <v-text-field
              name="title"
              label="Title"
              id="title"
              v-model="editedTitle"
              type="title"
              autocomplete="title"
              required
            />
            <v-text-field
              name="slug"
              label="Slug"
              id="slug"
              v-model="editedSlug"
              type="slug"
              autocomplete="slug"
              required
            />
            <v-btn
              class="ml-0"
              color="success"
              large
              @click="onSaveChanges"
            >
              <v-icon left>mdi-plus</v-icon>
              Create
            </v-btn> -->
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    // data () {
    //   return {
    //     editedTitle: this.page.title,
    //     editedSlug: this.page.slug
    //   }
    // },
    // props: ['id'],
    computed: {
      loading () {
        return this.$store.getters.loading
      },
      page () {
        return this.$store.getters.loadedPage(this.$route.params.key)
      }
    },
    // methods: {
    //   onSaveChanges () {
    //     const pageData = {
    //       id: this.page.id,
    //       title: this.editedTitle,
    //       slug: this.editedSlug
    //     }
    //     this.$store.dispatch('updatePageData', pageData)
    //     this.$router.push('/admin/pages')
    //   }
    // }
  }
</script>

<style>
</style>
