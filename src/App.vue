<template>
  <v-app id="inspire" style="background: #f4f6f9">
    <v-navigation-drawer
      v-if="!$vuetify.breakpoint.lgAndUp"
      v-model="drawer"
      :clipped="$vuetify.breakpoint.lgAndUp"
      app
      color="#f5f5f5"
    >
      <v-list nav color="#f5f5f5">
        <v-list-item
          v-for="(item, i) in btnItems"
          :key="i"
          link
          @click="$vuetify.goTo(`#${item}`)"
        >
          <v-list-item-content>
            <v-list-item-title>{{ item }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      fixed
      app
      elevate-on-scroll
      class="appbar"
      :clipped-left="$vuetify.breakpoint.lgAndUp"
    >
      <v-container>
        <v-row align="center" justify="space-between">
          <v-col class="d-flex align-center">
            <v-app-bar-nav-icon
              @click.stop="drawer = !drawer"
              v-if="!$vuetify.breakpoint.lgAndUp"
            />
            <v-toolbar-title
              style="cursor: pointer"
              class="font-weight-bold headline"
            >
              <v-icon large color="accent">
                mdi-feather
              </v-icon>
              Hero<span class="accent--text">UI</span>
            </v-toolbar-title>
          </v-col>
          <v-col class="text-right" v-if="$vuetify.breakpoint.lgAndUp">
            <v-btn
              text
              v-for="(item, i) in btnItems"
              :key="i"
              @click="$vuetify.goTo(`#${item}`)"
            >
              {{ item }}
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-app-bar>

    <v-content>
      <v-sheet dark>
        <v-img
          src="https://cdn.pixabay.com/photo/2020/04/17/14/16/mountains-5055387_1280.jpg"
          height="100vh"
          width="100vw"
        >
          <v-container class="fill-height">
            <v-row align="center" justify="center">
              <v-col class="text-center">
                <h3 class="display-2">
                  <span class="welcome">
                    Welcome To Our Studio!
                  </span>
                </h3>
                <h1 class="display-4 my-8 font-weight-black">
                  IT'S NICE TO MEET YOU
                </h1>

                <v-btn
                  x-large
                  color="accent"
                  class="mt-5"
                  href="https://github.com/AGDholo/agency"
                  target="_black"
                >
                  <v-icon left>
                    mdi-download
                  </v-icon>
                  Free Download
                </v-btn>
              </v-col>
            </v-row>
          </v-container>
        </v-img>
      </v-sheet>

      <v-container>
        <v-sheet color="transparent" id="SERVICES">
          <div class="pt-12 text-center">
            <h3 class="display-1 font-weight-blod">
              SERVICES
            </h3>
            <p class="body-2 my-3">
              <span class="welcome">
                Lorem ipsum dolor sit amet consectetur.
              </span>
            </p>
          </div>

          <v-row justify="center" align="center" class="mt-5">
            <v-col
              cols="12"
              md="4"
              v-for="(item, i) in services"
              :key="i"
              class="text-center"
            >
              <v-icon size="128" color="accent">
                {{ item.icon }}
              </v-icon>
              <h4 class="title my-2">
                {{ item.title }}
              </h4>
              <p>
                {{ item.subtitle }}
              </p>
            </v-col>
          </v-row>
        </v-sheet>
      </v-container>

      <v-sheet id="PORTFOLIO">
        <v-container>
          <div class="pt-12 text-center">
            <h3 class="display-1 font-weight-blod">
              PORTFOLIO
            </h3>
            <p class="body-2 my-3">
              <span class="welcome">
                Lorem ipsum dolor sit amet consectetur.
              </span>
            </p>

            <v-row align="center" justify="center" class="mt-5">
              <v-col cols="12" md="4" v-for="(item, i) in 6" :key="i">
                <v-img
                  src="https://cdn.pixabay.com/photo/2020/05/06/12/01/compass-5137269_1280.jpg"
                >
                </v-img>

                <h4 class="title mt-2">
                  Threads
                </h4>
                <p class="body-2">
                  <span class="welcome">
                    Illustration
                  </span>
                </p>
              </v-col>
            </v-row>
          </div>
        </v-container>
      </v-sheet>

      <v-sheet color="transparent" id="ABOUT">
        <v-container>
          <div class="pt-12 text-center">
            <h3 class="display-1 font-weight-blod">
              ABOUT
            </h3>
            <p class="body-2 my-3">
              <span class="welcome">
                Lorem ipsum dolor sit amet consectetur.
              </span>
            </p>
          </div>

          <v-timeline>
            <v-timeline-item v-for="(n, i) in 4" :key="i" large>
              <template v-slot:icon>
                <v-avatar>
                  <img src="https://i.pravatar.cc/64" />
                </v-avatar>
              </template>
              <template v-slot:opposite>
                <span>2009-2011</span>
              </template>
              <v-card flat color="transparent">
                <v-card-title class="headline"
                  >Our Humble Beginnings</v-card-title
                >
                <v-card-text class="body-2">
                  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sunt
                  ut voluptatum eius sapiente, totam reiciendis temporibus qui
                  quibusdam, recusandae sit vero unde, sed, incidunt et ea quo
                  dolore laudantium consectetur!
                </v-card-text>
              </v-card>
            </v-timeline-item>
          </v-timeline>
        </v-container>
      </v-sheet>

      <v-sheet id="TEAM">
        <v-container>
          <div class="pt-12 text-center">
            <h3 class="display-1 font-weight-blod">
              OUR AMAZING TEAM
            </h3>
            <p class="body-2 my-3">
              <span class="welcome">
                Lorem ipsum dolor sit amet consectetur.
              </span>
            </p>
          </div>

          <v-row justify="center" align="center" class="mt-5">
            <v-col
              cols="12"
              md="4"
              v-for="(item, i) in 3"
              :key="i"
              class="text-center"
            >
              <v-avatar size="224">
                <v-img src="https://i.pravatar.cc/224"></v-img>
              </v-avatar>

              <h4 class="title mt-2">
                Kay Garland
              </h4>
              <p class="body-2">
                Lead Designer
              </p>

              <div>
                <v-btn icon color="primary">
                  <v-icon>
                    mdi-twitter
                  </v-icon>
                </v-btn>
                <v-btn icon color="primary">
                  <v-icon>
                    mdi-facebook
                  </v-icon>
                </v-btn>
                <v-btn icon color="primary">
                  <v-icon>
                    mdi-instagram
                  </v-icon>
                </v-btn>
              </div>
            </v-col>

            <v-col cols="12" md="8" class="text-center mt-5 body-2">
              <p>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aut
                eaque, laboriosam veritatis, quos non quis ad perspiciatis,
                totam corporis ea, alias ut unde.
              </p>
            </v-col>
          </v-row>
        </v-container>
      </v-sheet>

      <v-sheet dark id="CONTACT">
        <v-img
          src="https://static-map.tesla.com/v1/map?screen_type=desktop&map_type=world"
          gradient="to top right, rgba(100,115,201,.33), rgba(25,32,72,.7)"
        >
          <v-container class="fill-height">
            <v-row justify="center" align="center" class="mt-5">
              <v-col cols="12">
                <div class="pt-12 text-center">
                  <h3 class="display-1 font-weight-blod">
                    CONTACT US
                  </h3>
                  <p class="body-2 my-3">
                    <span class="welcome">
                      Lorem ipsum dolor sit amet consectetur.
                    </span>
                  </p>
                </div>
              </v-col>

              <v-col cols="12" md="6">
                <v-text-field label="Your Name*" solo light></v-text-field>
                <v-text-field label="Your Email*" solo light></v-text-field>
                <v-text-field label="Your Phone*" solo light></v-text-field>
              </v-col>

              <v-col cols="12" md="6" class="fill-height">
                <v-textarea
                  light
                  outlined
                  solo
                  name="input-7-4"
                  label="Your Message*"
                ></v-textarea>
              </v-col>

              <v-col cols="12" class="text-center">
                <v-btn x-large color="accent">
                  Send Message
                </v-btn>
              </v-col>
            </v-row>
          </v-container>
        </v-img>
      </v-sheet>
    </v-content>

    <v-footer>
      <v-container>
        <v-row align="center" justify="space-between">
          <v-col>
            <div>
              Copyright &copy; Your Website {{ new Date().getFullYear() }}
            </div>
          </v-col>

          <v-col class="text-center">
            <div>
              <v-btn icon color="primary">
                <v-icon>
                  mdi-twitter
                </v-icon>
              </v-btn>
              <v-btn icon color="primary">
                <v-icon>
                  mdi-facebook
                </v-icon>
              </v-btn>
              <v-btn icon color="primary">
                <v-icon>
                  mdi-instagram
                </v-icon>
              </v-btn>
            </div>
          </v-col>

          <v-col class="text-right">
            <a text class="accent--text">
              Privacy Policy
            </a>
            <a text class="pl-2 accent--text">
              Terms of Use
            </a>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    dialog: false,
    drawer: null,
    btnItems: ["SERVICES", "PORTFOLIO", "ABOUT", "TEAM", "CONTACT"],
    services: [
      {
        icon: "mdi-store",
        title: "E-Commerce",
        subtitle:
          "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit.",
      },
      {
        icon: "mdi-laptop",
        title: "Responsive Design",
        subtitle:
          "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit.",
      },
      {
        icon: "mdi-lock",
        title: "Web Security",
        subtitle:
          "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit.",
      },
    ],
  }),
};
</script>

<style lang="scss">
.display-2,
.body-2 {
  .welcome {
    font-family: "Droid Serif", -apple-system, BlinkMacSystemFont, "Segoe UI",
      Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji",
      "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji" !important;
    font-style: italic;
  }
}
</style>
