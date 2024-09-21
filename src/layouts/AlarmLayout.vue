<template>
  <q-layout
    id="AlarmLayout"
    view="lHh lpR lFf"
    @contextmenu.prevent
    class="bg-base-200 overflow-hidden"
  >
    <q-drawer side="right" v-model="drawerModel" :width="100" class="bg-blue">
    </q-drawer>

    <q-page-container class="h-screen">
      <q-page class="h-full py-1">
        <q-splitter
          v-if="!$q.screen.xl"
          v-model="splitterModel2"
          class="w-full h-full"
          separator-class="bg-transparent"
          :separator-style="separatorWidth"
        >
          <template v-slot:before>
            <div class="workBench">
              <CaseBench />
            </div>
          </template>

          <template v-slot:after>
            <div class="workBench"></div>
          </template>
        </q-splitter>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
import { useQuasar } from "quasar";
import CaseBench from "./CaseBench/CaseBench.vue";

const $q = useQuasar();
$q.screen.setSizes({ xl: 3000 });

const drawerModel = ref(false);

const splitterModel1 = ref(29);
const splitterModel2 = ref(50); //59
const separatorWidth = "width: 4px";

const splitterModel = ref(70);
</script>

<style lang="scss">
#AlarmLayout {
  .workBench {
    // @apply h-full border-primary border dark:border-2 dark:rounded-xl overflow-hidden;
    @apply h-full border-primary border-2 rounded-xl overflow-hidden;
  }

  .q-drawer--right {
    width: calc(50% - 2px) !important;
  }
}
</style>
