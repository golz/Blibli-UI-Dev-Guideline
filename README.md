# Pyeongyang UI Code Style Guide

Standardization for developing pyeongyang UI with reasonable performance approach


## Getting Started
Before Continue to the content make sure you already read and understand this following concept or tutorials

[Block Element Modifier](http://getbem.com/)
[Airbnb Javascript Style Guide](https://github.com/airbnb/javascript)
[VueJs](https://vuejs.org/)


## Table of Contents

1. CSS 
2. VueJs

## CSS

In Pyeongyang UI we are agreed to use scss
```scss

// bad approach

.header {}
.header__left {}
.header__middle {}
.header__middle__search {}
.header__right {}

// bad approach

.header {}
.left {}
.middle {}
.middle .search {}
.right {}

// good approach

.header {
  &__left {}
  &__middle {
    &__search {}
  }
  &__right {}
}

// best approach
//break the chain if you're already inside element

.header {
   &__left {}
   &__middle {
     .search {}
   }
   &__right {}
 }

```

##Vue Js

Use VueJs files template by this following order
```vue
<template>
</template>

//use external javascript from js folder
<script src="./js/${fileName}"></script>

//use scss style and scoped the style
<style lang="scss" scoped></style>

```
Use Javascript template by this following order. use as needed. No need create all this lifecycle Hooks!
```js
export default {
  name: 'App',
  components: {},
  data () {
    return {}
  },
  beforeCreate(){},
  created () {
    //Will be execute before the UI being rendered
    //Used for important API Calls
  },
  beforeMount (){},
  mounted () {
    //Will be execute After the UI being rendered
    //Used for DOM manipulation and less important API Calls
  },
  computed: {},
  methods: {},
  watch: {},
  beforeDestroy: {},
  destroyed: {}
}

```


