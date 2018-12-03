<template>
  <v-app>
    <v-toolbar app class="red darken-4">
      <v-toolbar-side-icon>
        <img src="./assets/logo.svg" height="40" width="40">
      </v-toolbar-side-icon>
      <v-toolbar-items v-for="button in toolbar_buttons">
        <v-btn
          color="white"
          flat
          :href="button.link"
          target="_blank"
        > {{ button.name }}</v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-content>
      <v-item-group>
        <v-container>
          <v-layout column>
            <v-flex
              py-4
              xs12
            >
            <v-layout justify-center>
              <h1>Filter News Items</h1>
            </v-layout>
            </v-flex>
            <v-flex
              xs12
            >
              <v-layout justify-center>
                <v-btn
                  href="https://albanycentergallery.org/news?field_press_type_target_id=1"
                  target="_blank">
                    Gallery News
                </v-btn>
                <v-btn
                  href="https://albanycentergallery.org/news?field_press_type_target_id=2"
                  target="_blank">
                    Press Coverage
                </v-btn>
              </v-layout>
            </v-flex>
          </v-layout>
        </v-container>
      </v-item-group>
      <v-layout v-for="item in news_items">
        <NewsItem
          :image="item.image"
          :title="item.title"
          :description="item.description"
          :more="item.more"
        />
      </v-layout>
    </v-content>

    <v-footer
    dark
    height="auto"
  >
    <v-card
      color="#B71C1C"
      class="flex py-4"
      flat
      tile
    >
      <v-card-title>
        <v-flex xs2 md2>
          <v-flex xs12 md12 pl-2>
            <v-toolbar-side-icon>
              <img src="./assets/logo.svg" height="80" width="80">
            </v-toolbar-side-icon>
          </v-flex>
          <v-flex xs12 md12 pt-5>
          <v-icon
            v-for="i in 3" :key="i">
            info
          </v-icon>
          </v-flex>
        </v-flex>
        <v-flex xs5 md5>
          <h1> Location </h1>
          <p> 488 Broadway, Suite 107 Albany, NY 12207</p>
          <h1> Contact </h1>
          <p> 518.462.4775 director@albanycentergallery.org</p>
        </v-flex>
        <v-flex xs5 md5>
          <h1> Hours </h1>
          <p> Tuesday - Saturday Noon - 5pm, Or by appointment</p>
          <v-btn
            text-color="black"
            color="white"
            href="https://squareup.com/store/albanycentergallery/"
            target="_blank"><span style="color:black">Donate</span></v-btn>
        </v-flex>
      </v-card-title>
      <v-card-actions class="red darken-4 justify-center">
        Copyright &copy; Albany Center Gallery, 2018
      </v-card-actions>
    </v-card>
  </v-footer>
  </v-app>
</template>

<style>
  .v-item-group {
    background-color: lightgray;
  }
</style>

<script>
import NewsItem from './components/NewsItem'

export default {
  name: 'App',
  components: {
    NewsItem
  },
  data () {
    return {
      toolbar_buttons: [
        {
          name: 'About ACG',
          link: 'https://albanycentergallery.org/about'
        },
        {
          name: 'News',
          link: 'https://albanycentergallery.org/about'
        },
        {
          name: 'Events & Exhibits',
          link: 'https://albanycentergallery.org/about'
        },
        {
          name: 'Join & Support',
          link: 'https://albanycentergallery.org/about'
        },
        {
          name: 'Rentals',
          link: 'https://albanycentergallery.org/about'
        },
        {
          name: 'Gallery Archive',
          link: 'https://albanycentergallery.org/about'
        },
        {
          name: 'Store',
          link: 'https://albanycentergallery.org/about'
        },
        {
          name: 'Contact',
          link: 'https://albanycentergallery.org/about'
        }
      ],
      news_items: [
        {
          image: "https://albanycentergallery.org/sites/default/files/2018-11/members-show-small.jpg",
          title: "Annual Members' Show",
          description: "Join us for our Annual Members' Show, featuring over \
            125 works of art by local and regional artists! Visit our Facebook \
            event for updates and sneak peeks. Exhibit Dates: Friday, \
            December 7, 2018 to Friday, January 19, 2019 Opening Reception:  \
            1st Friday, December 7, 5 to 8 p.m. ",
          more: 'https://albanycentergallery.org/events/annual-members-show'
        },
        {
          image: "https://albanycentergallery.org/sites/default/files/2018-10/Call_for_Art_MembersShow_EDITED.png",
          title: "Artist Opportunity! Call for Art: Annual Members' Show",
          description: "We invite you to be part of our Members’ Show! \
            Visit our Submittable page for submission guidelines and to submit.\
            Join or renew your membership here.",
          more: 'https://albanycentergallery.org/events/artist-opportunity-call-art-annual-members-show'
        },
        {
          image: "https://albanycentergallery.org/sites/default/files/2018-10/IG_2-sm.jpg",
          title: "Keep It Surreal Gala",
          description: "Save the Date: Saturday, November 17, 2018 Mark your \
            calendars and come Keep It Surreal with us on Saturday, November 17th\
            at our benefit of the year! RSVP to our Facebook event for the latest\
            news and updates. Spend the evening unlocking your subconscious\
            mind, networking with other art enthusiasts, and celebrating \
            creative visions.",
          more: 'https://albanycentergallery.org/events/keep-it-surreal-gala'
        },
        {
          image: "https://albanycentergallery.org/sites/default/files/2018-10/Robert%20Cartmell%20Celebration%20of%20Life%20small.png",
          title: "Celebration of Robert Cartmell's Life",
          description: "We invite you to join us for a celebration of life in \
            honor of Robert Cartmell on Wednesday, October 24 from 5:30 p.m. to\
            7:30 p.m. at Albany Center Gallery. Family, friends and supporters \
            are encouraged to gather at ACG to share fond memories and celebrate\
            the creative life of Mr. Cartmell.",
            more: 'https://albanycentergallery.org/events/celebration-robert-cartmells-life'
        },
        {
          image: "https://albanycentergallery.org/sites/default/files/2018-09/still.life_._exhibit.jpg",
          title: "Announcing our next exhibit: Still. Life.",
          description: "Experience interpretations of 'Still Life' by regional\
            artists at Albany Center Gallery Exhibiting Artists: Paul Chapman,\
            Matt Chinian, Robert Gullie, Harry Orlyk, Andrew Pellettieri, Corey\
            Pitkin, Takeyce Walter, and Robert Whiting Exhibit Dates: October\
            30 to November 24, 2018 Opening Reception: 1st Friday, November\
            2, 5 to 8 p.m.",
          more: 'https://albanycentergallery.org/events/announcing-our-next-exhibit-still-life'
        }
      ]
    }
  }
}
</script>
