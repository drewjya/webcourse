<script lang="ts" setup>
import { watch } from "vue";
import { useRoute } from "vue-router";
const q = ref("");
const route = useRoute();
const isActive = ref(false);
watch(route, () => {
  console.log(route);
  isActive.value = false;
});
</script>

<template>
  <div id="navbar" class="bg-indigo-600">
    <div class="col-span-3 flex justify-start items-center">
      <div>Logo</div>
    </div>
    <div class="col-span-4 flex justify-end items-center">
      <UInput
        v-model="q"
        name="q"
        placeholder="Search..."
        icon="i-heroicons-magnifying-glass-20-solid"
        autocomplete="off"
        :ui="{ icon: { trailing: { pointer: '' } } }"
      >
        <template #trailing>
          <UButton
            v-show="q !== ''"
            color="gray"
            variant="link"
            icon="i-heroicons-x-mark-20-solid"
            :padded="false"
            @click="q = ''"
          />
        </template>
      </UInput>
    </div>
    <div class="col-span-5 h-16 text-sm font-bold">
      <div class="h-full hidden lg:block">
        <ul class="flex h-full items-center space-x-4 justify-end">
          <NuxtLink
            to="/"
            class="relative h-full flex justify-center px-2 hover:bg-indigo-300"
          >
            <li class="nav-item my-auto">Home</li>
            <div
              class="absolute h-[0.4rem] w-full bg-sky-500 rounded-lg bottom-0"
              v-if="route.fullPath == '/'"
            ></div>
          </NuxtLink>
          <NuxtLink
            to="/courses"
            class="relative h-full flex justify-center px-2 hover:bg-indigo-300"
          >
            <li class="nav-item my-auto">Daftar Kursus</li>
            <div
              class="absolute h-[0.4rem] w-full bg-sky-500 rounded-lg bottom-0"
              v-if="route.fullPath == '/courses'"
            ></div>
          </NuxtLink>
          <NuxtLink
            to="/about"
            class="relative h-full flex justify-center px-2 hover:bg-indigo-300"
          >
            <li class="nav-item my-auto">Tentang Kami</li>
            <div
              class="absolute h-[0.4rem] w-full bg-sky-500 rounded-lg bottom-0"
              v-if="route.fullPath == '/about'"
            ></div>
          </NuxtLink>
          <NuxtLink
            to="/login"
            class="relative h-full flex justify-center px-2 hover:bg-indigo-300"
          >
            <li class="nav-item my-auto">Masuk / Daftar</li>
            <div
              class="absolute h-[0.4rem] w-full bg-sky-500 rounded-lg bottom-0"
              v-if="route.fullPath == '/login'"
            ></div>
          </NuxtLink>
        </ul>
      </div>
      <div class="block lg:hidden h-full">
        <div class="flex h-full items-center justify-end">
          <button
            class="flex flex-col h-12 w-12 justify-center items-center group"
            @click="isActive = !isActive"
          >
            <div
              class="h-0.5 w-6 my-0.5 rounded-full bg-white transition ease transform duration-300"
              :class="isActive ? 'rotate-45 translate-y-1.5' : ''"
            ></div>
            <div
              class="h-0.5 w-6 my-0.5 rounded-full bg-white transition ease transform duration-300"
              :class="isActive ? 'opacity-0' : ''"
            ></div>
            <div
              class="h-0.5 w-6 my-0.5 rounded-full bg-white transition ease transform duration-300"
              :class="isActive ? '-rotate-45 -translate-y-1.5' : ''"
            ></div>
          </button>

          <div class="relative w-0">
            <div
              v-if="isActive"
              class="absolute top-8 right-0 bg-indigo-600 p-5 px-1 z-50"
            >
              <ul class="w-max space-y-2 flex flex-col">
                <NuxtLink to="/">
                  <li
                    class="rounded-md px-4 py-1 hover:bg-indigo-300"
                    :class="route.fullPath == '/' ? 'bg-indigo-300' : ''"
                  >
                    Home
                  </li>
                </NuxtLink>

                <NuxtLink to="/courses">
                  <li
                    class="rounded-md px-4 py-1 hover:bg-indigo-300"
                    :class="route.fullPath == '/courses' ? 'bg-indigo-300' : ''"
                  >
                    Daftar Kursus
                  </li>
                </NuxtLink>
                <NuxtLink to="/about">
                  <li
                    class="rounded-md px-4 py-1 hover:bg-indigo-300"
                    :class="route.fullPath == '/about' ? 'bg-indigo-300' : ''"
                  >
                    Tentang Kami
                  </li>
                </NuxtLink>
                <NuxtLink to="/login">
                  <li
                    class="rounded-md px-4 py-1 hover:bg-indigo-300"
                    :class="route.fullPath == '/login' ? 'bg-indigo-300' : ''"
                  >
                    Masuk / Daftar
                  </li>
                </NuxtLink>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
#navbar {
  color: white;
  display: grid;
  grid-template-columns: repeat(12, minmax(0, 1fr));
  padding: 0px 1rem;
}
</style>
