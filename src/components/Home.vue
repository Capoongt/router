<!-- Home.vue -->
<template>
  <div class="container text-center">
    <div class="row">
      <div class="col mt-5" v-for="(restaurant, index) in travelList" :key="index">
        <div class="card" style="width: 18rem">
          <img :src="restaurant.imagesP" class="card-img-top" :width="sizeW" :height="sizeH" />
          <div class="card-body">
            <h2>ร้านที่ : {{ index + 1 }}</h2>
            <h5 class="card-title">{{ restaurant.name }}</h5>
            <p class="card-text">ราคาเริ่ม : {{ restaurant.price }}</p>
            <button
              class="btn btn-danger"
              data-bs-toggle="modal"
              data-bs-target="#staticBackdrop"
              @click="goToOtherComponent(restaurant.name, restaurant.imagesP, index)"
            >
              ยืนยัน
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue' // import ref

export default {
  methods: {
    goToOtherComponent(name, imagesP, index) {
      // ส่งค่าไปยังคอมโพเนนต์ OtherComponent.vue ผ่านคิวรี่พารามิเตอร์
      this.$router.push({
        name: 'other',
        query: {
          index: index,
          restaurantName: name,
          restaurantImagesP: imagesP
        }
      })
    }
  },
  setup() {
    const travelList = ref([
      {
        name: ' Five-SeveN ',
        price: 1500,
        imagesP:
          'https://community.akamai.steamstatic.com/economy/image/-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgposLOzLhRlxfbGTj5X09q_goW0hPLiNrXukmJQ-txOh-zF_Jn4xgPl-UBrMjugdYSWc1U-Zg2D-VLsweq7gpC1uMmYnXU2v3F2tCvcnB2pwUYbcUSIkFw'  },
      {
        name: 'Desert Eagle',
        price: 1200,
        imagesP:
         'https://community.akamai.steamstatic.com/economy/image/-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgposr-kLAtl7PLZTjlH_9mkgIWKkPvxDLDEm2JS4Mp1mOjG-oLKhF2zowdyYmD7I4LAe1c8YQuGqwK6yLu518O96pzMzHUxsyknsHvYnBO0gk4aO_sv26LIOeeP5w'  },
      {
        name: 'M4A1-S',
        price: 1500,
        imagesP:
          'https://community.akamai.steamstatic.com/economy/image/-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgpou-6kejhz2v_Nfz5H_uO1gb-Gw_alIITfn2xZ_MhwmOz--InxgUG55Rc5MTyiJNSUIAc9N13VrwS_wO3ogZLu786az3QyuHQktCyIyhzh10xSLrs4fBuRSpM'   },
      {
        name: ' Tiger Tooth',
        price: 1000,
        imagesP:
          'https://community.akamai.steamstatic.com/economy/image/-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgpovbSsLQJfw-bbeQJD4uOinYeOhcj7IbrfkW5u5Mx2gv2P8Y-mjVDk-0JoMW6hJoaXdlc5NwqDqwDvkr_u08Tu6sycynFguych4GGdwUKPWgFGtQ' },
      {
        name: 'USP-S',
        price: 6257.66,
        imagesP:
          'https://community.akamai.steamstatic.com/economy/image/-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgpoo6m1FBRp3_bGcjhQ09-jq5WYh8jkIbLfgnhF-sBwh9bN_Iv9nBrtrUY-MD33co-RJlQ9NVHW_wO9k-y6gsW_7cyanHZkunUr4XnbnB23n1gSOU78gfTH'},
      {
        name: 'AWP',
        price: 578.03,
        imagesP:
          'https://community.akamai.steamstatic.com/economy/image/-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgpot621FABz7PLfYQJO5dG0m7-Ymfb_NoTdn2xZ_Isn2rCZoY_w2VHhqEI9ZzigJYbAegU6ZVyB8wO5lOm5gp7o6JTBm3M2pGB8sn-9jb_y' }
        ])
    

    const sizeW = 350
    const sizeH = 250

    return {
      // return ตัวแปรออกมาจาก setup
      travelList,
      sizeW,
      sizeH
    }
  }
}
</script>
