<template>
  <StudentForm
    :title="title"
    v-model:nis="formData.nis"
    v-model:nama="formData.nama"
    v-model:nilaiTugas.number="formData.nilaiTugas"
    @save-event="save"
  />
  <div class="absolute text-xl font-semibold right-4 top-52 mr-20">
    Nilai Rata-rata =
    <span v-if="students.length > 0">{{ findAverage() }}</span>
    <span v-else>0</span>
  </div>
  <div class="flex flex-wrap justify-center">
    <StudentList
      v-for="[index, student] of Object.entries(students)"
      :key="index"
      :nis="student.nis"
      :nama="student.nama"
      :nilaiTugas="student.nilaiTugas"
    />
  </div>
</template>

<script>
  export default {
    data() {
      return {
        title: "Student List",
        formData: {
          nis: '',
          nama: '',
          nilaiTugas: 0,
        },
        students: [],
        sum: 0,
      }
    },
    methods: {
      addData() {
        this.students.push(this.formData)
      },
      clearData() {
        this.formData = {
          nis: '',
          nama: '',
          nilaiTugas: 0,
        }
      },
      findAverage() {
        let sum = 0
        for (let i = 0; i < this.students.length; i++) {
          sum += this.students[i].nilaiTugas
        }
        return parseInt(sum / this.students.length)
      },
      save() {
        this.addData()
        this.clearData()
      },
    },
    computed: {},
  }
</script>
