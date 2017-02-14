# vue-iscroll-view

[IScroll](https://github.com/cubiq/iscroll) component for Vue 2.0

## Install

```bash
$ npm i vue-iscroll-view
$ npm i iscroll
```

```
import IScroll from 'iscroll'
import IScrollView from 'vue-iscroll-view'

Vue.use(Iscroll)
```

## Get Start

```vue
<template>
  <iscroll-lite class="scroll-view">
    Your contents
  </iscroll-lite>
</tempalte>

<script>

export default {
  components: {
    IscrollLite
  }
}
</script>

<style>
.scroll-view {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  overflow: hidden;
}
</style>
```

## Usage

### Set IScroll options

```vue
<template>
  <iscroll-lite :options="{preventDefault: false}">
    Your contents
  </iscroll-lite>
</tempalte>

<script>
import IscrollLite from 'vue-iscroll-lite'
export default {
  components: {
    IscrollLite
  }
}
</script>
```

### Listen IScroll events

```vue
<template>
  <iscroll-lite @scrollStart="log">
    Your contents
  </iscroll-lite>
</tempalte>

<script>
import IscrollLite from 'vue-iscroll-lite'
export default {
  components: {
    IscrollLite
  },
  methods: {
    log (iscroll) {
      console.log(iscroll)
    }
  }
}
</script>
```

### Call IScroll instance functions

```vue
<template>
  <div>
    <iscroll-lite ref="iscroll">
      Your contents
    </iscroll-lite>
    <button @click="scrollToTop">Scroll To Top</button>
  </div>
</tempalte>

<script>
import IscrollLite from 'vue-iscroll-lite'
export default {
  components: {
    IscrollLite
  },
  methods: {
    scrollToTop () {
      const iscroll = this.$refs.iscroll
      iscroll.scrollTo(0, 0, 100)
      iscroll.refresh()
    }
  }
}
</script>
```

### Custom events

- pullUp
- pullDown

```vue
<template>
  <iscroll-lite @pullUp="refresh", @pullDown="load">
    Your contents
  </iscroll-lite>
</tempalte>

<script>
import IscrollLite from 'vue-iscroll-lite'
export default {
  components: {
    IscrollLite
  },
  methods: {
    refresh (iscroll) {
      // Refresh current data
    },
    load (iscroll) {
      // Load new data
    }
  }
}
</script>
```
