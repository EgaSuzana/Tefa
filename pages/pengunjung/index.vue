<template>
  <div class="container fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">Riwayat Kunjungan</h2>
        <div class="my-3">
          <input type="search" class="form-control form-control-lg rounded-5" placeholder=" filter...">
        </div>
        <div class="my-3 text-muted">menampilkan 1 dari 1</div>
        <table class="table">
          <thead>
            <tr>
              <td>#</td>
              <td>Nama</td>
              <td>Keanggotaan</td>
              <td>Waktu</td>
              <td>Keperluan</td>
            </tr>
          </thead>
          <tbody>
            <tr>
            <td>1</td>
            <td>Ega Suzana</td>
            <td>Siswa</td>
            <td>28 februari 2024</td>
            <td>Meminjam buku</td>
            </tr>
          </tbody>
        </table>
        <nuxt-link to="http://localhost:3000">
        <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">Kembali</button>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>