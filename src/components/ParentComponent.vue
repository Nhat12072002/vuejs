<!-- ParentComponent.vue -->
<template>
  <div class="container">
    <h1>Component Cha</h1>
    <p>Thông điệp từ cha: {{ thongDiepCha }}</p>
    <p>Thông điệp từ Component Con: {{ thongDiepCon }}</p>
    <ChildComponent :thongDiep="thongDiepCha" @guiSuKien="nhanSuKienTuCon" />
    <AnotherChildComponent @suKienKhac="nhanSuKienTuConKhac"></AnotherChildComponent>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';
import AnotherChildComponent from './AnotherChildComponent.vue';
export default {
  data() {
    return {
      thongDiepCha: 'Xin chào từ Component Cha!',
      thongDiepCon: '',
    };
  },
  methods: {
    nhanSuKienTuCon(thongDiep) {
      this.thongDiepCon = thongDiep;
    },
    nhanSuKienTuConKhac(thongDiep) {
      this.thongDiepCon = thongDiep;
    },
  },
  components: {
    ChildComponent,
    AnotherChildComponent,
  },
};
</script>

<style scoped>
.container {
  max-width: 600px;
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
</style>