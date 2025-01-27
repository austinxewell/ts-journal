<script setup lang="ts">
import TheHeader from "@/components/TheHeader.vue";
import EntryEditor from "./components/EntryEditor.vue";
import EntryCard from "@/components/EntryCard.vue";
import { reactive } from "vue";
import type User from "./types/User";
import type Entry from "./types/Entry";

const user: User = reactive({
  id: 1,
  username: "danielkeylly_io",
  settings: [],
});
const entries: Entry[] = reactive([]);

const handleCreateEntry = (entry: Entry) => {
  entries.push(entry);
};
</script>

<template>
  <main class="container m-auto p-10">
    <TheHeader />
    <EntryEditor @create="handleCreateEntry" />
    <ul>
      <li v-for="entry in entries">
        {{ entry }}
        <EntryCard />
      </li>
    </ul>
  </main>
</template>
