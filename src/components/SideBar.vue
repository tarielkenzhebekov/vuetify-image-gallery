<script setup>
  const emit = defineEmits(['selectOption']);
</script>

<template>
    <v-navigation-drawer
        expand-on-hover
        rail
      >

        <v-list>
            <v-list-item
                prepend-avatar="https://randomuser.me/api/portraits/men/38.jpg"
                title="Shumkarbek Barpyev"
                subtitle="shumkar@example.com"
            ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item v-on:click="emit('selectOption', false)" prepend-icon="mdi-image" title="Color Gallery" value="colorful"></v-list-item>
          <v-list-item v-on:click="emit('selectOption', true)" prepend-icon="mdi-dialpad" title="Grayspace Gallery" value="grayspace"></v-list-item>
        </v-list>

      </v-navigation-drawer>

</template>