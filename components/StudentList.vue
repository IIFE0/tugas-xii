<template>
  <div class="bg-sky-700 w-96 mt-4 p-4 rounded-md mx-2 shadow-red-700 shadow-md">
    <p class="text-xl">NIS: {{ nis }}</p>
    <h3 class="text-2xl font-bold">Nama Siswa: {{ nama }}</h3>
    <p class="text-xl">Nilai Tugas: {{ nilaiTugas }}</p>
  </div>
</template>

<script>
  export default {
    props: {
      nis: String,
      nama: String,
      nilaiTugas: Number,
    },
  }
</script>
