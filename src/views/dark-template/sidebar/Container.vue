<template>
  <v-card color="grey darken-3" dark>
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          Stijn
          <span
            class="light-blue--text text--lighten-3"
            >Rovers</span
          >
        </h1>
        <span>
          A challenge-loving Space Engineer
        </span>
      </div>

      <sidebar-section
        :options="sections.info"
      />
      <sidebar-section
        :options="sections.socials"
      />
      <sidebar-section
        :options="sections.hobbies"
      >
        <template v-slot:item="{ item }">
          <v-chip>
            <v-avatar>
              <v-icon>
                {{ item.icon }}
              </v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>
      <sidebar-section
        :options="sections.languages"
      >
        <template v-slot:items="{ items }">
          <v-container pa-0>
            <v-layout
              wrap
              class="text-xs-center"
            >
              <template
                v-for="(item, i) in items"
              >
                <v-flex :key="i" md3 sm4 xs6>
                  <v-progress-circular
                    rotate="360"
                    size="65"
                    width="2"
                    :value="item.value"
                    color="white"
                    class="ma-2"
                  >
                    {{ item.text }}
                  </v-progress-circular>
                </v-flex>
              </template>
            </v-layout>
          </v-container>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import Avatar from '@/views/dark-template/sidebar/Avatar'
import SidebarSection from '@/views/dark-template/sidebar/Section'
export default {
  name: 'Sidebar',
  components: { SidebarSection, Avatar },
  data() {
    return {
      sections: {
        info: {
          title: 'INFO',
          items: [
            {
              name: 'Email',
              icon: 'mdi-email',
              text:
                's.p.rovers@student.tudelft.nl',
            },
            {
              name: 'Website',
              icon: 'mdi-web',
              text: 'stijnrovers.nl',
            },
            {
              name: 'Birth Date',
              icon: 'mdi-cake-variant',
              text: 'JUL 2, 1994',
            },
            {
              name: 'Habitation',
              icon: 'mdi-map-marker',
              text: 'Delft, The Netherlands',
            },
          ],
        },
        socials: {
          title: 'SOCIALS',
          items: [
            {
              icon: 'mdi-github',
              text: 'github.com/Pinsterr',
              link:
                'https://github.com/Pinsterr',
            },
            {
              icon: 'mdi-linkedin',
              text:
                'linkedin.com/in/stijnrovers',
              link:
                'https://linkedin.com/in/stijnrovers',
            },
            {
              icon: 'mdi-twitter',
              text:
                'twitter.com/stijnrovers',
              link:
                'https://twitter.com/stijnrovers',
            },
            {
              icon: 'mdi-instagram',
              text:
                'instagram.com/stijnrovers',
              link:
                'https://instagram.com/stijnrovers',
            },
          ],
        },
        hobbies: {
          title: 'HOBBIES',
          items: [
            {
              icon: 'mdi-bullseye',
              text: 'Achieving Goals',
            },
            {
              icon: 'mdi-bike',
              text: 'Cycling',
            },
            {
              icon: 'mdi-image-filter-hdr',
              text: 'Nature',
            },
            {
              icon: 'mdi-auto-fix',
              text: 'Customizing',
            },
            {
              icon: 'mdi-karate',
              text: 'Sports',
            },
            {
              icon: 'mdi-music',
              text: 'Music',
            },
            {
              icon: 'mdi-account-group',
              text: 'Collaborating',
            },
            {
              icon:
                'mdi-book-open-page-variant',
              text: 'Learning',
            },
            {
              icon:
                'mdi-android-debug-bridge',
              text: 'Robotics',
            },
            {
              icon: 'mdi-hammer-wrench',
              text: 'DIY',
            },
          ],
        },
        languages: {
          title: 'LANGUAGES',
          items: [
            {
              text: 'Dutch',
              value: 100,
            },
            {
              text: 'English',
              value: 80,
            },
            {
              text: 'German',
              value: 30,
            },
          ],
        },
      },
    }
  },
}
</script>

<style scoped>
.sidebar {
  background: #2e2e2e;
}
</style>
