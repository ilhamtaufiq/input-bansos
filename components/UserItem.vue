<template>
  <div class="bg-gray-100 mx-auto max-w-12xl bg-white py-20 px-12 lg:px-24 shadow-xl mb-24">
      <p>Nama: {{user.nama}}</p>
      <p>NIK: {{user.nik}}</p>
      <p>Nomor KK: {{user.no_kk}}</p>
      <p>Foto KTP: <img :src="user.previewKTP" alt=""> </p>
      <p>Foto KK: <img :src="user.previewKK" alt=""> </p>
      <p>Umur: {{user.umur}}</p>
      <p>Jenis Kelamin: {{user.jk}}</p>
      <p>Provinsi: {{user.provinsi}}</p>
      <p>Kabupaten/Kota: {{kabkota}}</p>
      <p>Kecamatan: {{kec}}</p>
      <p>Kelurahan/Desa: {{keldes}}</p>
      <p>Alamat: {{user.alamat}} - {{user.rt}}/{{user.rw}}</p>
      <p>Penghasilan Sebelum Pandemi: {{user.p_before}}</p>
      <p>Penghasilan Setelah Pandemi: {{user.p_after}}</p>
      <p>Alasan Membutuhkan Bantuan: {{user.alasan}} {{user.alasan_lainnya}}</p>
  </div>
    <!-- <div class="float-left">
        <div class="md:container md:mx-auto">            
            <img :src="user.previewKTP" alt="">
        </div>
    </div> -->
</template>

<script>
    export default {
        nama: "UserItem",
        props: ["user"]
    }
</script>

<style scoped>
 img {
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 150px;
}
</style>