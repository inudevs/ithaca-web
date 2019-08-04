<template>
  <div id="app">
    <div class="content">
      <router-view/>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.content {
  display: flex;
  justify-content: center;
  padding-left: 10rem;
  padding-right: 10rem;

  @media (max-width: 900px) {
    padding-left: 6rem;
    padding-right: 6rem;
  }

  @media (max-width: 600px) {
    padding-left: 3rem;
    padding-right: 3rem;
    display: block;
  }

  @media (max-width: 400px) {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }
}
</style>
