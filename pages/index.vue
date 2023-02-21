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
          <h1>Welcome to Hynse Server!</h1>
          <p>Join our Minecraft survival multiplayer server today and enjoy playing with other players from all around the world. Our server is family-friendly, and we have a welcoming community of players who are always happy to help out newcomers.</p>
          <v-card>
            <v-card-title>Server Details</v-card-title>
            <v-card-text>
              <p><b>IP Address:</b> play.hynse.xyz</p>
              <p><b>Version:</b> 1.19.3</p>
              <p><b>Server Rules:</b></p>
              <ul>
                <li>No griefing or stealing</li>
                <li>No cheating or exploiting bugs</li>
                <li>No offensive language or behavior</li>
              </ul>
            </v-card-text>
          </v-card>
        </v-container>
      </v-main>
    </v-app>
  </template>
  
  <script>
  export default {
    data: () => ({
      drawer: false,
      miniVariant: false,
      menuItems: [
        { title: 'Home', icon: 'mdi-home', to: '/' },
        { title: 'About', icon: 'mdi-information-outline', to: '/about' },
        { title: 'Join Us', icon: 'mdi-account-multiple-outline', to: '/join' },
        { title: 'Gallery', icon: 'mdi-image', to: '/gallery' },
        { title: 'Contact Us', icon: 'mdi-email', to: '/contact' },
      ],
    }),
  };
  </script>
  
  <style>
  @import '~vuetify/dist/vuetify.min.css';
  
  h1 {
    font-size: 32px;
    font-weight: bold;
    margin-top: 32px;
  }
  
  p {
    font-size: 18px;
    line-height: 1.5;
    margin-top: 16px;
  }
  
  ul {
    margin-top: 8px;
    margin-left: 16px
  }

  li {
  font-size: 16px;
  line-height: 1.2;
  margin-top: 8px;
}

v-card {
  margin-top: 32px;
}

v-card-title {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 16px;
}

v-card-text {
  font-size: 18px;
}