<template>
    <v-app>
      <v-navigation-drawer app v-model="drawer" :mini-variant="miniVariant" @update:mini-variant="val => miniVariant = val">
        <v-list>
          <v-list-item>
            <v-list-item-avatar>
              <img src="https://media.discordapp.net/attachments/1033187106215964793/1067706813811785779/ok.png?width=703&height=703">
            </v-list-item-avatar>
            <v-list-item-content>
              <div class="subtitle-1 font-weight-bold">Hynse</div>
              <div class="caption">A Minecraft survival multiplayer server</div>
            </v-list-item-content>
          </v-list-item>
          <v-divider></v-divider>
          <v-list-item v-for="item in menuItems" :key="item.title" :to="item.to" router>
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-app-bar app>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title>My SMP Server</v-toolbar-title>
      </v-app-bar>
      <v-main>
        <v-container>
          <h1 class="smp-title">Gallery</h1>
          <v-row>
            <v-col v-for="image in images" :key="image.id" cols="12" md="4">
              <v-card class="image-card">
                <v-img :src="image.src" :alt="image.alt" height="200" contain class="zoomable"></v-img>
                <v-card-title class="title">{{ image.title }}</v-card-title>
                <v-card-subtitle>{{ image.subtitle }}</v-card-subtitle>
                <v-card-text>{{ image.description }}</v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>
    </v-app>
  </template>
  
  <script>
export default {
  methods: {
  toggleZoom(image) {
    if (image.classList.contains('zoomed')) {
      image.classList.remove('zoomed');
    } else {
      image.classList.add('zoomed');
    }
  },
  updateCursor(image) {
    if (image.classList.contains('zoomed')) {
      image.style.cursor = 'zoom-out';
    } else {
      image.style.cursor = 'zoom-in';
    }
  }
},
    data() {
      return {
        images: [
          {
            id: 1,
            src: "https://lh3.googleusercontent.com/pw/AMWts8DRVcW6KBpmaSvivjMkZq3RsTsEPjAskMx01Z61gNAfXWibhUxqDYxfhEVgn00gaAn1qabRMxBIGxRJm7SyN__HVb89QwLF6LBe7y7NAPXZli95gOYbjgpjaNp5O57Ol3l24m1kMSsj5HOxdVHVQVA=w1920-h810-no?authuser=0",
            alt: "Image 1",
            title: "Image 1",
            subtitle: "Subtitle 1",
            description: "Description 1",
          },
          {
            id: 2,
            src: "https://media.discordapp.net/attachments/1069604502124109854/1070706241468379186/huge_2023-02-02_21.03.15.png",
            alt: "Image 2",
            title: "Image 2",
            subtitle: "Subtitle 2",
            description: "Description 2",
          },
          {
            id: 3,
            src: "https://media.discordapp.net/attachments/1069604502124109854/1070749303305420903/huge_2023-02-02_23.35.22.png",
            alt: "Image 3",
            title: "Image 3",
            subtitle: "Subtitle 3",
            description: "Description 3",
          },
          {
            id: 4,
            src: "https://media.discordapp.net/attachments/1069604502124109854/1070749309445886053/huge_2023-02-02_23.34.53.png",
            alt: "Image 4",
            title: "Image 4",
            subtitle: "Subtitle 4",
            description: "Description 4",
          },
          {
            id: 5,
            src: "https://media.discordapp.net/attachments/1069604502124109854/1070749352382955601/huge_2023-02-02_23.40.54.png",
            alt: "Image 5",
            title: "Image 5",
            subtitle: "Subtitle 5",
            description: "Description 5",
          },
          {
            id: 6,
            src: "https://media.discordapp.net/attachments/1069604502124109854/1070751462788968478/huge_2023-02-03_00.03.31.png",
            alt: "Image 6",
            title: "Image 6",
            subtitle: "Subtitle 6",
            description: "Description 6",
          },
        ],
        drawer: false,
      miniVariant: false,
      menuItems: [
        { title: 'Home', icon: 'mdi-home', to: '/' },
        { title: 'About', icon: 'mdi-information-outline', to: '/about' },
        { title: 'Join Us', icon: 'mdi-account-multiple-outline', to: '/join' },
        { title: 'Gallery', icon: 'mdi-image', to: '/gallery' },
        { title: 'Contact Us', icon: 'mdi-email', to: '/contact' },
      ]
      };
    },

  };
</script>

</script>

<style scoped>
.smp-title {
  text-align: center;
  font-size: 40px;
  margin: 20px 0;
}

.image-card {
  margin: 10px;
  transition: transform 0.5s ease;
}

.image-card:hover {
  transform: scale(1.05);
}

.zoomable {
  cursor: zoom-in;
  transition: transform 0.5s ease;
}

.zoomed {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  margin: 0;
  z-index: 9999;
  border-radius: 0;
  transform: none !important;
  box-shadow: 0px 0px 50px #000000;
}
</style>