<template>
  <ContainerVue id="mentors">
    <HeadingVue front="Mentors" back="MENTORS" />
    <CBox
      :mx="{ base: '0rem', sm: '50px' }"
      justify="center"
      :mt="{ base: '2rem', sm: '5rem' }"
    >
      <CGrid
        :gap="{ base: '1rem', sm: '3rem' }"
        :template-columns="{
          base: 'repeat(2, 1fr)',
          sm: 'repeat(2, 1fr)',
          md: 'repeat(3, 1fr)',
          xl: 'repeat(4, 1fr)',
        }"
      >
        <CGridItem v-for="(person, index) in people" :key="index">
          <a :href="person.url" class="narrative animate-ease" target="_blank">
            <div class="image animate-ease">
              <img class="narrator" :src="person.image" />
            </div>
            <div class="text">
              <h2>{{ person.name }}</h2>
            </div>
          </a>
        </CGridItem>
      </CGrid>
    </CBox>
  </ContainerVue>
</template>

<script>
import { CBox, CGrid, CGridItem } from '@chakra-ui/vue'
import HeadingVue from './HeadingComponent.vue'
import ContainerVue from './Container.vue'
export default {
  components: {
    HeadingVue,
    ContainerVue,
    CBox,
    CGrid,
    CGridItem,
  },
  data() {
    return {
      people: [
        {
          name: 'Rishi Raj Jain',
          url: 'https://twitter.com/rishi_raj_jain_',
          image: require('~/assets/mentors/rishi.jpeg'),
        },
        {
          name: 'Dhiraj Chauhan',
          url: 'https://twitter.com/cdhiraj40',
          image: require('~/assets/mentors/dhiraj.jpeg'),
        },
        {
          name: 'Avinesh Tripathi',
          url: 'https://twitter.com/Avinesh__T',
          image: require('~/assets/mentors/avinesh.jpeg'),
        },
        {
          name: 'Aryan Kaushik',
          url: 'https://twitter.com/aryankaushik21',
          image: require('~/assets/mentors/aryan.jpg'),
        },
        {
          name: 'Ghulam Yazdani',
          url: 'https://twitter.com/iamyazreza',
          image: require('~/assets/mentors/ghulam.jpeg'),
        },
        {
          name: 'Manav Darji',
          url: 'https://twitter.com/manav24_',
          image: require('~/assets/mentors/manav.jpg'),
        },
        {
          name: 'Swastika Yadav',
          url: 'https://twitter.com/swastika0015',
          image: require('~/assets/mentors/swastika.png'),
        },
        {
          name: 'Aditya Thakur',
          url: 'https://twitter.com/adityathakurxd',
          image: require('~/assets/mentors/aditya.jpg'),
        },
        {
          name: 'Shubham Sah',
          url: 'https://twitter.com/ishubhamsah',
          image: require('~/assets/mentors/shubham.jpg'),
        },
        {
          name: 'Insha Ramin',
          url: 'https://twitter.com/Insharamin',
          image: require('~/assets/mentors/insha.jpg'),
        },
        {
          name: 'Daxeel Soni',
          url: 'https://twitter.com/daxeelsoni',
          image: require('~/assets/mentors/daxeel.jpg'),
        },
        {
          name: 'Harsh Shah',
          url: 'https://twitter.com/harshcrop',
          image: require('~/assets/mentors/harsh.jpg'),
        },
        {
          name: 'Bhargav Patel',
          url: 'https://www.linkedin.com/in/bhargav-p-patel/',
          image: require('~/assets/mentors/bhargav.jpg'),
        },
      ],
    }
  },
  mounted() {
    this.people.sort((a, b) => {
      if (a.name < b.name) {
        return -1
      }
      if (a.name > b.name) {
        return 1
      }
      return 0
    })
  },
}
</script>
<style lang="scss" scoped>
.narrative {
  border-radius: 40px;
  background: linear-gradient(
    180deg,
    #142137 0%,
    #0b121f 99.99%,
    rgba(20, 33, 55, 0) 100%
  );
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  height: 100%;
  align-items: center;
  padding: 25px;

  &:hover {
    background: linear-gradient(180deg, #0b3b52 3.72%, #0b121f 141.1%);

    .image {
      border: 3px solid #fefaf4;
    }
  }

  .image {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    border: 3px solid transparent;
    position: relative;

    .narrator {
      width: 100%;
      height: 100%;
      border-radius: 50%;
    }
  }

  .text {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    flex-grow: 1;
    margin-top: 20px;

    h2 {
      font-family: 'Poppins';
      font-style: normal;
      font-weight: 700;
      font-size: 1.25rem;
      line-height: 28px;
      color: #fefaf4;
      text-align: center;
    }
  }

  @include respond-below(xs) {
    padding: 1rem;
    .image {
      width: 100px;
      height: 100px;
    }

    .text {
      h2 {
        font-size: 1rem;
        line-height: 1.2rem;
      }

      p {
        font-size: 0.6rem;
        line-height: 19px;
      }
    }
  }
}
</style>
