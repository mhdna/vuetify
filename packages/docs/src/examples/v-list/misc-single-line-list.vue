<template>
  <v-card
    class="mx-auto"
    max-width="500"
  >
    <v-toolbar color="deep-purple-accent-4">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>New Chat</v-toolbar-title>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-toolbar>

    <v-list>
      <v-list-subheader>Recent chat</v-list-subheader>

      <v-list-item
        v-for="chat in recent"
        :key="chat.title"
      >
        <template v-slot:prepend>
          <v-avatar>
            <v-img :src="chat.avatar"></v-img>
          </v-avatar>
        </template>

        <v-list-item-title>{{ chat.title }}</v-list-item-title>

        <template v-slot:append>
          <v-avatar>
            <v-icon :color="chat.active ? 'deep-purple accent-4' : 'grey'">
              mdi-message-outline
            </v-icon>
          </v-avatar>
        </template>
      </v-list-item>
    </v-list>

    <v-divider></v-divider>

    <v-list>
      <v-list-subheader>Previous chats</v-list-subheader>

      <v-list-item
        v-for="chat in previous"
        :key="chat.title"
      >
        <template v-slot:prepend>
          <v-avatar>
            <v-img :src="chat.avatar"></v-img>
          </v-avatar>
        </template>

        <v-list-item-title v-text="chat.title"></v-list-item-title>
      </v-list-item>
    </v-list>
  </v-card>
</template>

<script setup>
  const recent = [
    {
      active: true,
      avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
      title: 'Jason Oner',
    },
    {
      active: true,
      avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
      title: 'Mike Carlson',
    },
    {
      avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
      title: 'Cindy Baker',
    },
    {
      avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
      title: 'Ali Connors',
    },
  ]
  const previous = [{
    title: 'Travis Howard',
    avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
  }]
</script>

<script>
  export default {
    data: () => ({
      recent: [
        {
          active: true,
          avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
          title: 'Jason Oner',
        },
        {
          active: true,
          avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
          title: 'Mike Carlson',
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
          title: 'Cindy Baker',
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
          title: 'Ali Connors',
        },
      ],
      previous: [{
        title: 'Travis Howard',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
      }],
    }),
  }
</script>
