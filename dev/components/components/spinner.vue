<template>
  <div>
    <div class="layout-padding">
      <q-field
        icon="format size"
        :label="`Size: ${size}px`"
      >
        <q-range label v-model="size" :min="20" :max="256" />
      </q-field>

      <q-field
        icon="palette"
        label="Color"
      >
        <div class="row no-wrap">
          <q-input
            v-model="color"
            class="col"
            float-label="Color Palette"
          />
          <q-select
            class="col"
            v-model="color"
            float-label="Quick Pick"
            :options="colorOptions"
          />
        </div>
      </q-field>

      <p class="caption">
        Hover over them to see their names
      </p>

      <div style="margin-top: 20px" class="group">
        <div v-for="spinner in spinners" class="inline-block">
          <component
            :is="`q-spinner-${spinner}`"
            :size="size"
            :color="color"
          ></component>
          <q-tooltip :offset="[0, 8]">{{spinner}}</q-tooltip>
        </div>
      </div>

      <p class="caption">
        Default Theme Spinner:
        <q-spinner :color="color" :size="size" style="margin-left: 1rem;" />
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      size: 36,
      color: 'primary',
      spinners: [
        'audio', 'ball', 'bars', 'circles', 'comment',
        'cube', 'dots', 'facebook', 'gears', 'grid', 'hearts',
        'hourglass', 'infinity', 'ios', 'mat', 'oval',
        'pie', 'puff', 'radio', 'rings', 'tail'
      ],
      colorOptions: [
        {
          label: 'Black',
          color: 'black',
          value: 'black'
        },
        {
          label: 'Primary',
          color: 'primary',
          value: 'primary'
        },
        {
          label: 'Secondary',
          color: 'secondary',
          value: 'secondary'
        },
        {
          label: 'Red',
          color: 'red',
          value: 'red'
        },
        {
          label: 'Green',
          color: 'green',
          value: 'green'
        },
        {
          label: 'Blue',
          color: 'blue',
          value: 'blue'
        }
      ]
    }
  }
}
</script>
