<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">BUKU</h2>
        <div class="my-3">
          <input type="search" class="form-control form-control-lg rounded-5" placeholder=" mau baca apa hari ini?">
        </div>
        <div class="my-3 text-muted">Menampilkan 3 dari 3</div>
        <div class="row">
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <nuxt-link to="/rincian">
                <img src="assets/buku1.png" class="cover" alt="buku">
                </nuxt-link>
              </div>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <nuxt-link to="/rincian/buku1">
                <img src="assets/pai.jpg" class="cover" alt="buku2">
              </nuxt-link>
              </div>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img src="assets/novel.jpg" class="cover" alt="buku3">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <nuxt-link to="http://localhost:3000">
        <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">Kembali</button>
        </nuxt-link>
</template>

<style scoped>
.card-body {
  width: 100%;
  height: 20em;
  padding: 0;
}
.cover {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: 0 30;
}
</style>