<template>
  <h1 class="text-3xl font-bold mb-4 text-center text-gray-800 p-2">
    {{ title }}
  </h1>
  <div class="m-auto p-4 w-1/2 bg-sky-300 rounded shadow-slate-500 shadow-md">
    <form action="" method="post">
      <div class="mb-2 flex flex-col">
        <label for="nis" class="mb-2">Nomor Induk Siswa:</label>
        <input
          id="nis"
          type="text"
          name="nis"
          class="text-sm p-1"
          placeholder="Masukkan Nomor Induk Siswa"
          :value="nis"
          @input="$emit('update:nis', $event.target.value)"
        />
      </div>
      <div class="mb-2 flex flex-col">
        <label for="nama">Nama:</label>
        <input
          id="nama"
          type="text"
          name="nama"
          class="p-1"
          placeholder="Masukkan Nama"
          :value="nama"
          @input="$emit('update:nama', $event.target.value)"
        />
      </div>
      <div class="mb-2 flex flex-col">
        <label for="nilaiTugas">Nilai:</label>
        <input
          :value="nilaiTugas"
          id="nilaiTugas"
          type="number"
          name="nilaiTugas"
          class="p-1"
          min="0"
          @input="$emit('update:nilaiTugas', $event.target.value)"
        />
      </div>
      <div class="mt-2 float-right">
        <button
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
          @click.prevent="$emit('saveEvent')"
        >
          Simpan
        </button>
      </div>
      <div class="clear-both"></div>
    </form>
  </div>
</template>

<script>
  export default {
    props: {
      title: String,
      nis: String,
      nama: String,
      nilaiTugas: Number,
    },
    emits: ['updated:nis', 'updated:nama', 'updated:nilaiTugas', 'saveEvent'],
    methods: {
      save() {
        this.$emit('saveEvent')
      },
    },
  }
</script>
