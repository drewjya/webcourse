<script lang="ts" setup>
import type { DropdownItem } from "@nuxt/ui/dist/runtime/types";

definePageMeta({
  layout: "default",
});
useHead({
  title: "Daftar Kursus",
});

let data = [0, 1, 2, 3, 4, 5];

let categories: DropdownItem[][] = [
  [
    {
      label: "Kursus",
    },
    {
      label: "Pelatihan",
    },
  ],
];
</script>

<template>
  <div class="h-full flex flex-col bg-gray-100">
    <div class="w-full p-9 relative bg-indigo-600 rounded-b-full shadow">
      <div class="text-center text-white text-4xl font-bold">
        Tersedia Kursus Gratis
      </div>
      <div class="text-center text-white text-4xl font-bold">
        Kuasai Skill-Skill
      </div>
      <div class="text-center text-white text-4xl font-bold">
        Untuk Jadi Freelancer
      </div>
    </div>
    <div class="grow">
      <div class="h-full py-[3%] px-[10%] flex flex-col">
        <div class="flex justify-center items-center space-x-2 mb-8">
          <UDropdown :items="categories" :popper="{ arrow: true }">
            <UButton
              color="white"
              label="Semua Kategori"
              trailing-icon="i-heroicons-chevron-down-20-solid"
            />
          </UDropdown>

          <UDropdown :items="categories" :popper="{ arrow: true }">
            <UButton
              color="white"
              label="Semua Tipe"
              trailing-icon="i-heroicons-chevron-down-20-solid"
            />
          </UDropdown>
          <UDropdown :items="categories" :popper="{ arrow: true }">
            <UButton
              color="white"
              label="Urut Berdasarkan"
              trailing-icon="i-heroicons-chevron-down-20-solid"
            />
          </UDropdown>
          <UButton color="indigo" label="Cari" />
        </div>
        <div class="grow">
          <div class="flex flex-wrap gap-5">
            <div v-for="i in data" :key="i" class="w-72 bg-white">
              <div>Key Perfor</div>
              <div class="flex space-x-1">
                <div>1</div>
                <div>2</div>
                <div>3</div>
              </div>
              <div>img</div>
              <div>
                <div class="profile flex">
                  <div>av</div>
                  <div>
                    <div>name</div>
                    <div>title</div>
                  </div>
                </div>
                <div class="flex">
                  <div>tema</div>
                  <div>tema</div>
                </div>
                <div>content</div>
                <div class="flex">
                  <div>price</div>
                  <div>button</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
