<template>
  <div class="container-fluid w-full">
    <nav class="bg-stone-900 w-full h-16 fixed">
      <div class="w-full h-full flex justify-start gap-4 items-center p-2">
        <img class="w-8" src="../assets/logo.png" alt="" />
        <div class="flex justify-start gap-3 items-center">
          <a class="text-white" href="#">Home</a>
          <a class="text-white" href="#">About me</a>
          <a class="text-white" href="#">Portfolio</a>
          <a class="text-white" href="#">Contact</a>
        </div>
      </div>
    </nav>
    <div
      class="w-full min-h-screen flex flex-col justify-center place-items-center p-5 bg-stone-950"
    >
      <!-- <div
        class="mb-4 w-60 h-60 rounded-full animate-pulse transition-all duration-150 bg-gray-300"
      ></div> -->
      <img
        class="mb-4 w-60 h-60 rounded-full"
        src="../assets/images/profile.jpg"
        alt=""
      />
      <!-- <div
        class="mt-4 w-60 h-6 rounded-xl animate-pulse transition-all duration-150 bg-gray-300"
      ></div> -->
      <p class="mt-4 text-2xl font-bold text-white">Hi, Nice to meet you!</p>
      <!-- <div
        class="mt-4 w-96 h-6 rounded-xl animate-pulse transition-all duration-150 bg-gray-300"
      ></div> -->
      <p class="mt-4 text-lg text-white">
        My name is Muhammad Valensyah Alfansyuri
      </p>
      <!-- <div
        class="mt-4 w-52 h-6 rounded-xl animate-pulse transition-all duration-150 bg-gray-300"
      ></div> -->
      <p class="mt-4 text-white">
        And i'm a <strong>Frontend Developer</strong>
      </p>
    </div>
    <div
      id="theme-section"
      class="w-full h-screen relative py-10 overflow-hidden bg-sky-300"
    >
      <label
        class="mt-4 ml-10 relative inline-flex items-center cursor-pointer"
      >
        <input
          type="checkbox"
          value=""
          @change="toggleTheme"
          class="sr-only peer"
        />
        <div
          class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-4 peer-focus:ring-blue-300 dark:peer-focus:ring-blue-800 rounded-full peer dark:bg-gray-700 peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all dark:border-gray-600 peer-checked:bg-blue-600"
        ></div>
        <span
          :class="
            [
              `ml-3 text-sm font-medium`,
              dark ? 'text-gray-300' : 'text-gray-900',
            ].join(' ')
          "
          >{{ dark ? "Night" : "Day" }}</span
        >
      </label>
      <div id="orb" class="absolute top-10 right-10"></div>

      <img
        src="../assets/icons/star.png"
        :class="
          [
            `stars animate-pulse transition-all duration-150 ease-out absolute sm:top-14 top-32 right-1/4`,
            dark ? 'block' : 'hidden',
          ].join(' ')
        "
        alt=""
      />
      <img
        src="../assets/icons/star.png"
        :class="
          [
            `stars animate-pulse transition-all duration-150 ease-out absolute sm:top-10 top-36 right-2/3`,
            dark ? 'block' : 'hidden',
          ].join(' ')
        "
        alt=""
      />
      <img
        src="../assets/icons/star.png"
        :class="
          [
            `stars animate-pulse transition-all duration-150 ease-out absolute sm:top-32 top-44 right-1/2`,
            dark ? 'block' : 'hidden',
          ].join(' ')
        "
        alt=""
      />
      <img
        src="../assets/icons/star.png"
        :class="
          [
            `stars animate-pulse transition-all duration-150 ease-out absolute sm:top-28 top-72 right-1/3`,
            dark ? 'block' : 'hidden',
          ].join(' ')
        "
        alt=""
      />
      <img
        src="../assets/icons/star.png"
        :class="
          [
            `stars animate-pulse transition-all duration-150 ease-out absolute sm:top-40 top-72 right-3/4`,
            dark ? 'block' : 'hidden',
          ].join(' ')
        "
        alt=""
      />

      <div class="w-full h-full relative">
        <div id="land" class="absolute bottom-0 w-full h-32 bg-green-500">
          <div class="w-fulll-h-full relative">
            <img
              src="../assets/images/house.png"
              class="absolute sm:-top-32 sm:translate-x-1/2 sm:left-1/2 sm:w-40 -top-12 translate-x-1/2 left-1/2 w-16"
              alt=""
            />
            <img
              src="../assets/images/house.png"
              class="absolute sm:-top-32 sm:translate-x-1/4 sm:left-1/4 sm:w-40 -top-12 translate-x-1/4 left-1/4 w-16"
              alt=""
            />
            <img
              src="../assets/images/forest.png"
              class="absolute sm:-top-32 sm:left-24 sm:w-40 -top-12 left-10 w-16"
              alt=""
            />
            <img
              src="../assets/images/forest.png"
              class="absolute sm:-top-32 sm:left-3/4 sm:w-40 -top-12 left-3/4 w-16"
              alt=""
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      position: 10,
      dark: false,
    };
  },
  methods: {
    toggleTheme(e) {
      if (e.target.checked) {
        this.moveImg(true);
      } else {
        this.moveImg(false);
      }
    },
    async moveImg(stat) {
      this.dark = stat;
      let orb = document.getElementById("orb");
      let theme = document.querySelector("#theme-section");

      if (this.dark) {
        orb.classList.add("animate-drown");
        orb.classList.remove("animate-rise");
        theme.classList.add("animate-dark");
        theme.classList.remove("animate-light");
      } else {
        orb.classList.add("animate-rise");
        orb.classList.remove("animate-down");
        theme.classList.add("animate-light");
        theme.classList.remove("animate-dark");
      }
    },
  },
};
</script>
<style lang="scss">
#orb {
  width: 100px;
  height: 100px;
  background: url("../assets/icons/sun.png");
  background-size: 100% auto;
  // background-color: #fbbf24;
  // background-color: #fcd34d;
  // background-color: #fb923c;
  // background-color: #facc15;
  // background-color: #020617;
  // background-color: #3b82f6;
  // background-color: #a855f7;
}
.animate-drown {
  animation-name: drown;
  animation-duration: 2.5s;
  animation-timing-function: ease-in-out;
  animation-fill-mode: forwards;
}
.animate-rise {
  animation-name: rise;
  animation-duration: 2.5s;
  animation-timing-function: ease-in-out;
  animation-fill-mode: forwards;
}

.animate-dark {
  animation-name: darkTheme;
  animation-duration: 2.5s;
  animation-timing-function: ease-in-out;
  animation-fill-mode: forwards;
}

.animate-light {
  animation-name: lightTheme;
  animation-duration: 2.5s;
  animation-timing-function: ease-in-out;
  animation-fill-mode: forwards;
}

@keyframes drown {
  0% {
    opacity: 1;
    top: 40px;
    display: block;
    background: url("../assets/icons/sun.png");
    background-size: 100% auto;
  }
  10% {
    opacity: 1;
    top: 20px;
    display: block;
    background: url("../assets/icons/sun.png");
    background-size: 100% auto;
  }
  50% {
    opacity: 0;
    top: 50%;
    display: none;
    background: url("../assets/icons/sun.png");
    background-size: 100% auto;
  }
  60% {
    opacity: 0;
    top: 50%;
    display: none;
    background: url("../assets/icons/moon.png");
    background-size: 100% auto;
  }
  90% {
    opacity: 1;
    top: 20px;
    display: block;
    background: url("../assets/icons/moon.png");
    background-size: 100% auto;
  }
  100% {
    opacity: 1;
    top: 40px;
    display: block;
    background: url("../assets/icons/moon.png");
    background-size: 100% auto;
  }
}

@keyframes rise {
  0% {
    opacity: 1;
    top: 40px;
    display: block;
    background: url("../assets/icons/moon.png");
    background-size: 100% auto;
  }
  10% {
    opacity: 1;
    top: 20px;
    display: block;
    background: url("../assets/icons/moon.png");
    background-size: 100% auto;
  }
  50% {
    opacity: 0;
    top: 50%;
    display: none;
    background: url("../assets/icons/moon.png");
    background-size: 100% auto;
  }
  60% {
    opacity: 0;
    top: 50%;
    display: none;
    background: url("../assets/icons/sun.png");
    background-size: 100% auto;
  }
  90% {
    opacity: 1;
    top: 20px;
    display: black;
    background: url("../assets/icons/sun.png");
    background-size: 100% auto;
  }
  100% {
    opacity: 1;
    top: 40px;
    display: block;
    background: url("../assets/icons/sun.png");
    background-size: 100% auto;
  }
}

@keyframes darkTheme {
  0% {
    background-color: rgb(125 211 252);
  }
  100% {
    background-color: rgb(8 47 73);
  }
}

@keyframes lightTheme {
  0% {
    background-color: rgb(8 47 73);
  }
  100% {
    background-color: rgb(125 211 252);
  }
}

@media (max-width: 400px) {
  #orb {
    width: 64px;
    height: 64px;
  }
  .stars {
    width: 24px;
    height: 24px;
  }
}
</style>
