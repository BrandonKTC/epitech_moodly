<script>
const token1 =
  "77c6ed820b5ea43230a610a215437ab6de8902043d42732e9491209e74447c9bdc17194271c1daa671efa279b3dbc07357f18fce44154e393568b71c5fdf96981a6eab97bfafa7cbb7b6aea81f0a9bcfa61a560af1c00bf21c073eab078fb4c6b9c3ac3ca2e796f0b5b7760fb3550f717af419230f22aea5b11d45337d6497f4";

export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    async login() {
      const token = token1;
      localStorage.setItem("token", token);

      if (token) {
        if (
          token ===
          "77c6ed820b5ea43230a610a215437ab6de8902043d42732e9491209e74447c9bdc17194271c1daa671efa279b3dbc07357f18fce44154e393568b71c5fdf96981a6eab97bfafa7cbb7b6aea81f0a9bcfa61a560af1c00bf21c073eab078fb4c6b9c3ac3ca2e796f0b5b7760fb3550f717af419230f22aea5b11d45337d6497f4"
        ) {
          this.$router.push("/Mood");
        } else if (token === "") {
          this.$router.push("/Dashboard");
        } else {
          console.error("Type de jeton inattendu");
        }
      } else {
        console.error("Format de jeton invalide");
      }
    },
  },
};
</script>

<template>
  <div
    class="flex min-h-full flex-1 flex-col justify-center px-6 py-12 lg:px-8"
  >
    <div class="sm:mx-auto sm:w-full sm:max-w-sm">
      <h1
        class="mt-10 text-center text-4xl font-bold leading-9 tracking-tight text-yellow-400"
      >
        Epitech Moodly
      </h1>
    </div>

    <div class="mt-10 sm:mx-auto sm:w-full sm:max-w-sm">
      <form class="space-y-6" action="#" method="POST" @submit.prevent="login">
        <div>
          <label
            for="email"
            class="block text-sm font-medium leading-6 text-black"
            >Email</label
          >
          <div class="mt-2">
            <input
              id="email"
              v-model="email"
              name="email"
              type="email"
              autocomplete="email"
              required=""
              class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-yellow-200 placeholder:text-yellow-300 focus:ring-2 focus:ring-inset focus:ring-yellow-500 sm:text-sm sm:leading-6 p-2"
            />
          </div>
        </div>

        <div>
          <div class="flex items-center justify-between">
            <label
              for="password"
              class="block text-sm font-medium leading-6 text-black"
              >Mot de passe</label
            >
          </div>
          <div class="mt-2">
            <input
              id="password"
              name="password"
              v-model="password"
              autocomplete="current-password"
              required=""
              class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-yellow-200 placeholder:text-yellow-300 focus:ring-2 focus:ring-inset focus:ring-yellow-500 sm:text-sm sm:leading-6 p-2"
            />
          </div>
        </div>

        <div>
          <button
            type="submit"
            class="flex w-full justify-center rounded-md bg-rose-400 px-3 py-1.5 text-sm font-semibold leading-6 text-white shadow-sm hover:bg-rose-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
          >
            Se connecter
          </button>
        </div>
      </form>
    </div>
  </div>
</template>
