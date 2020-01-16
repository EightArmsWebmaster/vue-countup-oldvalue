<template>
  <div class="container">
    <!-- <span :class="active ? 'active': ''" v-countUp:onClassChange.once="{ startValue: 0, endValue: 120, expectedClass: 'active', options: { duration: 1 } }"></span> -->
<!--     <span :class="{ active : active }" v-countUp:onClassChange.once="{ startValue: 0, endValue: 120, expectedClass: 'active', options: { duration: 1 } }"></span> -->
    <span :class="getActiveClass()" v-countUp:onClassChange.once="{ startValue: 0, endValue: 120, expectedClass: 'active', options: { duration: 1 } }"></span>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  data(){
  	return {
  		active: false,
  	}
  },
  methods: {
  	getActiveClass(){
  		return this.active ? 'active' : '';
  	}
  },
  mounted(){
  	setTimeout(()=> {
  		this.active = true;
  	}, 1000);
  }


}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
