<script lang="ts" setup>
withDefaults(
  defineProps<{
    prefix?: string;
    person?: {
      firstname: string;
      lastname: string;
    };
  }>(),
  {
    prefix: "Bonjour",
    // la func permet d'éviter d'avoir le même objet pour toutes les instances du cmpt
    person: () => ({
      firstname: "firstname",
      lastname: "lastname",
    }),
  }
);

defineEmits<{
  demo: [firstname: string, lastname: string];
}>();

defineModel<string>();
</script>

<template>
  <p @click="$emit('demo', person.firstname, person.lastname)">
    {{ prefix }} {{ person.firstname }}
  </p>
</template>
