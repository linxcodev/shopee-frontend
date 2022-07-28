<script setup>
import Header from '@/Sections/Header.vue';
import { Head, Link } from "@inertiajs/inertia-vue3";

defineProps({
  canLogin: Boolean,
  canRegister: Boolean,
  laravelVersion: String,
  phpVersion: String,
});
</script>

<template>
  <Head title="Home" />

  <Header :canLogin="canLogin" />

  <div class="bg-[#f5f5f5]"> 
    <div class="max-w-6xl m-auto">
      kajhdfa
    </div>
  </div>
</template>