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
              <td>Kategori</td>
              <td>Waktu</td>
              <td>Keperluan</td>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(visitor,i) in visitors" :key="i">
            <td>{{ i+1 }}</td>
            <td>{{ visitor.nama }}</td>
            <td>{{ visitor.kategori.nama }}</td>
            <td>{{ visitor.tanggal }}, [[ visitor.waktu]]</td>
            <td>{{ visitor.keperluan.nama }}</td>
            </tr>
          </tbody>
        </table>
        <nuxt-link to="/">
        <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">Kembali</button>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()

const visitors = ref([])

const getPengunjung = async () => {
  const { data, error } = await supabase.from('pengunjung').select('*, keanggotaan(*), keperluan(*)')
  if(data) visitors.value = data
}
onMounted(() => {
  getPengunjung()
})
</script>