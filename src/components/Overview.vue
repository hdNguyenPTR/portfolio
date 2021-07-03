<template>
  <div>
    <Card title="Overview">
      <p class="lead">
        Hello, I'm <strong>{{ personal.full_name }}</strong>, a Software Engineer based in Sydney, Australia. Find me on
        <template v-for="(social, idx) in socials">
          <a
            :key="idx"
            :href="social.link"
            :style="{color: social.color}"
            target="_blank">
            {{ social.name }}
          </a>
          {{ idx !== socials.length - 1 ? ', ': ''}}{{ idx === socials.length - 2 ? 'and': ''}}
        </template>
      </p>
      <p>
        As a Software Engineer, I like to tackle modern problems with modern solutions. I want to create great products with good architecture, high scalability, and easy to maintain.
      </p>
      <p>
        I'm looking for opportunities to participate in challenging to learn more on the job, as I still want to chase my dream.
      </p>
      <div class="mt-5">
        <button class="btn btn-primary mr-3" @click="downloadResume">Download Resume</button>
      </div>
    </Card>
  </div>
</template>
<script>
import Card from './Card.vue'

export default {
  name: "Overview",
  props: {
    'socials': {
      type: Array,
      required: true,
      default: function() {
        return []
      }
    },
    'personal': {
      type: Object,
      required: true,
      default: function() {
        return {}
      }
    }
  },
  components: {
    Card
  },
  data: () => ({
    isPaid: false
  }),
  created() {
    if (process.isClient) {
      if (document.monetization) {
        document.monetization.addEventListener('monetizationstart', event => {
          if (document.monetization.state === 'started') {
            this.isPaid = true
          }
        });
      }
    }
  },
  methods: {
    downloadResume() {
      if (!this.isPaid) {
        window.open(this.coffeeDonateUrl, '_blank')
      } else {
        window.open('https://www.linkedin.com/in/ittus/', '_blank')
      }
    }
  }
}
</script>
<style lang="scss" scoped>
.lead {
  color: #000;
}
</style>
