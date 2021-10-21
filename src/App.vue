<template>
  <div id="app">
    <div class="container">
      <div class="row mt-5 justify-content-center">
        <div class="col-10">
          <div class="card">
          <div class="card-boy">
            <router-view />
          </div>
        </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  
}
</script>