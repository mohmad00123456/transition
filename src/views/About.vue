<template>
  <div class="about">
    <transition
      name="fade"
      appear
      @befor-enter="beforEnter"
      @enter="enter"
      @after-enter="afterEnter"
      @befor-leave="beforLeave"
      @leave="leave"
      @after-leave="afterLeave"
    >
      <h1 v-if="showTitle">About</h1>
    </transition>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam
      officia possimus delectus inventore quod quisquam culpa voluptas iusto,
      quae maiores quo dolorum, corporis laboriosam a dolore consequatur
      assumenda nam!
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam
      officia possimus delectus inventore quod quisquam culpa voluptas iusto,
      quae maiores quo dolorum, corporis laboriosam a dolore consequatur
      assumenda nam!
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam
      officia possimus delectus inventore quod quisquam culpa voluptas iusto,
      quae maiores quo dolorum, corporis laboriosam a dolore consequatur
      assumenda nam!
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showTitle: true,
    };
  },
  methods: {
    beforEnter() {
      console.log("beforEnter");
    },
    enter() {
      console.log("enter");
    },
    afterEnter() {
      console.log("AfterEnter");
      setTimeout(() => (this.showTitle = false), 3000);
    },
    beforLeave() {
      console.log("beforLeave");
    },
    leave() {
      console.log("leave");
    },
    afterLeave() {
      console.log("afterLeave");
      setTimeout(() => (this.showTitle = true), 1000);
    },
  },
};
</script>

<style>
.about {
  max-width: 600px;
  margin: 20px auto;
}

/* fade classes */

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}
.fade-enter-active,
.fade-leave-active {
  transition: all 3s ease;
}
</style>