<template>
  <v-chip-group
    :value="value"
    :show-arrows="false"
    :mobile-break-point="10000"
    class="px-2"
    multiple
    @change="(v) => $emit('input', v)"
  >
    <v-chip
      v-for="service in services"
      :key="service"
      :value="service"
      label
      active-class="primary--text"
    >
      <v-icon small>{{ `osm-${service}` }}</v-icon>
      <span class="pl-1">{{ $t(`services.${service}`) }}</span>
    </v-chip>
  </v-chip-group>
</template>

<script>
export default {
  props: {
    value: {
      type: Array,
      required: true
    },

    services: {
      type: Array,
      required: true
    }
  }
};
</script>
