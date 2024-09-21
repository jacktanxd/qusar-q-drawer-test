<template>
  <q-layout view="hHh Lpr lff" container>
    <q-header bordered>
      <div
        class="row items-center px-2 py-2 w-full bg-base-200 text-base-content"
      >
        <q-btn flat @click="drawerModel = !drawerModel" round dense icon="menu">
        </q-btn>
        <!-- <CallBar class="grow" /> -->
      </div>
    </q-header>
    <q-drawer
      v-model="drawerModel"
      :width="600"
      :breakpoint="700"
      elevated
      class="bg-red"
    >
      <!-- <CaseNew v-if="storeCall.calls.length" /> -->
    </q-drawer>

    <q-page-container> </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";

const drawerModel = ref(false);
</script>
