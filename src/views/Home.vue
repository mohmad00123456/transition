<template>
  <div class="home">
    <transition name="toasts">
      <Toast v-if="showToast" />
    </transition>
    <Todos @badValue="triggerToast" />
  </div>
</template>

<script>
import { ref } from "vue";
import Toast from "../components/Toast";
import Todos from "../components/Todos";

export default {
  components: { Toast, Todos },
  setup() {
    const showToast = ref(false);

    const triggerToast = () => {
      showToast.value = true;
      setTimeout(() => (showToast.value = false), 3000);
    };

    return { showToast, triggerToast };
  },
};
</script>

<style>
/* enterClass */
/* .toasts-enter-from {
  opacity: 0;
  transform: translateY(300px);
}
.toasts-enter-to {
  opacity: 1;
  transform: translateY(0);
} */
.toasts-enter-active {
  animation: wobble 1 s ease;
  /* transition: all 2s ease; */
}
.toasts-leave-from {
  opacity: 1;
  transform: translateY(0);
}
.toasts-leave-to {
  opacity: 0;
  transform: translateY(300px);
}
.toasts-leave-active {
  transition: all 1s ease;
}

/*   create animation   */

@keyframes wobble {
  /*هاد مشان الاحمر يهز على الجوانب*/
  0% {
    opacity: 0;
    transform: translateY(300px);
  }
  50% {
    opacity: 1;
    transform: translateY(0);
  }
  60% {
    transform: translateX(8px);
  }
  70% {
    transform: translateX(-8px);
  }
  80% {
    transform: translateX(4px);
  }
  90% {
    transform: translateX(-4px);
  }
  100% {
    transform: translateX(0);
  }
}
</style>