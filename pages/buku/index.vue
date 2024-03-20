<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4"> CARI BUKU</h2>
        <div class="my-3">
          <form @submit.prevent="getBooks">
          <input v-model="keyword" type="search" class="form-control form-control-lg rounded-5" placeholder=" mau baca apa hari ini?">
        </form>
      </div>
        <div class="my-3 text-muted">Menampilkan 3 dari 3</div>
        <div class="row">
          
          <div v-for="(book,i) in books" :key="i" class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <h3>{{ book.judul }}</h3>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <nuxt-link to="/">
        <button type="submit" class="btn btn-dark btn-lg rounded- px-5">Kembali</button>
        </nuxt-link>
</template>

<style scoped>
.cover {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: 0 30;
}
.input{
  background-color: #D9D9D9;
}
</style>
<script setup>
const supabase = useSupabaseClient()

const books = ref([])
const keyword = ref([])

const getbooks = async () => {
  const { data, error } = await supabase.from('buku').select(`*, kategori(*)`)
  .ilike('judul', `%${keyword.value}%`)
  if(data) books.value = data
}

onMounted(() => {
  getbooks()
})



</script>