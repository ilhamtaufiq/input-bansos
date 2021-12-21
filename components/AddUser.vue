<template>
<div>
  <form @submit="addUser">
      <div class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 flex flex-col">
        <div class="-mx-3 md:flex mb-6">
          <div class="md:w-1/2 px-3 mb-6 md:mb-0">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Nama
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="text" name="nama" v-model="nama" placeholder="Nama">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              NIK
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="number" name="nik" v-model="nik" placeholder="NIK">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Umur
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="number" name="umur" v-model="umur" placeholder="Umur">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Jenis Kelamin
            </label>
             <select class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" id="jk" name="jk" v-model="jk">
                <option value="Laki-Laki" >Laki-Laki</option>
                <option value="Perempuan">Perempuan</option>
              </select>
          </div>
        </div>
        <div class="-mx-3 md:flex mb-6">
          <div class="md:w-full px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Nomor Kartu Keluarga
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="number" name="no_kk" v-model="no_kk" placeholder="Nomor Kartu Keluarga">
          </div>
        </div>
        <div class="-mx-3 md:flex mb-6">
          <div class="md:w-1/2 px-3 mb-6 md:mb-0">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Foto KTP
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="file" accept="image/png" @change=uploadKTP placeholder="Upload Foto KTP">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Foto KK
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="file" accept="image/png" @change=uploadKK placeholder="Upload Foto KK">
          </div>
        </div>
        <div class="-mx-3 md:flex mb-6">
          <div class="md:w-1/2 px-3 mb-6 md:mb-0">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Provinsi
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="text" name="provinsi" v-model="provinsi" placeholder="Nama">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Kabupaten/Kota
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="text" name="kabkota" v-model="kabkota" placeholder="Kabupaten/Kota">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Kecamatan
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="text" name="kec" v-model="kec" placeholder="Kecamatan">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Keluarahan/Desa
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="text" name="keldes" v-model="keldes" placeholder="Kelurahan/Desa">
          </div>
        </div>
        <div class="-mx-3 md:flex mb-6">
          <div class="md:w-1/2 px-3 mb-6 md:mb-0">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Alamat
            </label>
            <textarea class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" name="alamat" v-model="alamat" placeholder="Alamat" />
          </div>
          <div class="md:w-1/2 px-3 mb-6 md:mb-0">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              RT
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded text-xs py-3 px-4 pr-8 mb-3" type="number" name="rt" v-model="rt" placeholder="RT">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              RW
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded text-xs py-3 px-4 pr-8 mb-3" type="number" name="rw" v-model="rw" placeholder="RW">
          </div>
        </div>
        <div class="-mx-3 md:flex mb-6">
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Penghasilan Sebelum Pandemi
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="number" name="p_before" v-model="p_before" placeholder="Penghasilan Sebelum Pandemi">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Penghasilan Setelah Pandemi
            </label>
            <input class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="number" name="p_after" v-model="p_after" placeholder="Penghasilan Setelah Pandemi">
          </div>
          <div class="md:w-1/2 px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Alasan
            </label>
             <select class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" name="alasan" v-model="alasan" id="alasan">
                <option value="Kehilangan pekerjaan">Kehilangan pekerjaan</option>
                <option value="Kepala keluarga terdampak atau korban Covid-19">Kepala keluarga terdampak atau korban Covid-19</option>
                <option value="Tergolong fakir/miskin semenjak sebelum Covid-19">Tergolong fakir/miskin semenjak sebelum Covid-19</option>
                <option value="Lainnya">Lainnya...</option>
              </select>          
          </div>
        </div>
        <div class="-mx-3 md:flex mb-6" v-if="alasan === 'Lainnya'">
          <div class="md:w-full px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Alasan
            </label>
            <textarea class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" type="text" name="alasan_lainnya" v-model="alasan_lainnya" placeholder="Alasan Lainnya..." />
          </div>
        </div>
        <div class="-mx-3 md:flex mb-6">
          <div class="md:w-full px-3">
            <label class="uppercase tracking-wide text-black text-xs font-bold mb-2">
              Saya menyatakan bahwa data yang diisikan adalah benar dan siap mempertanggungjawabkan apabila ditemukan ketidaksesuaian dalam data tersebut
            </label>
            <input type="checkbox" name="checked" v-model="checked" value="checked">
          </div>
          <div class="md:w-full px-3">
          </div>
          <div class="md:w-full px-3">
          </div>
        </div>
        <div class="-mx-3 md:flex mt-2">
          <div class="md:w-full px-3">
            <button class="md:w-full bg-gray-900 text-white font-bold py-2 px-4 border-b-4 hover:border-b-2 border-gray-500 hover:border-gray-100 rounded-full" type="submit">
              Simpan
            </button>
          </div>
        </div>
        <div>
          <p v-if="errors.length">
            <b>Please correct the following error(s):</b>
            <ul>
              <li v-for="error in errors">{{ error }}</li>
            </ul>
          </p>
        </div>
      </div>
    </form>
        <!-- <form @submit="addUser">
            <input type="text" name="nama" v-model="nama" placeholder="Nama">
            <input type="number" name="nik" v-model="nik" placeholder="NIK">
            <input type="number" name="no_kk" v-model="no_kk" placeholder="Nomor Kartu Keluarga">
            <input type="number" name="umur" v-model="umur" placeholder="Umur">
             <label for="jk">Jenis Kelamin</label>
              <select v-model="jk" name="jk" id="jk">
                <option value="Laki-Laki">Laki-Laki</option>
                <option value="Perempuan">Perempuan</option>
              </select> 
            <input type="text" name="provinsi" v-model="provinsi" placeholder="Provinsi"> 
            <input type="text" name="kabkota" v-model="kabkota" placeholder="Kabupaten/Kota"> 
            <input type="text" name="kec" v-model="kec" placeholder="Kecamatan"> 
            <input type="text" name="keldes" v-model="keldes" placeholder="Kelurahan/Desa"> 
            <input type="text" name="alamat" v-model="alamat" placeholder="Alamat">
            <input type="number" name="rt" v-model="rt" placeholder="RT">
            <input type="number" name="rw" v-model="rw" placeholder="RW">
            <input type="number" name="p_before" v-model="p_before" placeholder="Penghasilan Sebelum Pandemi">
            <input type="number" name="p_after" v-model="p_after" placeholder="Penghasilan Setelah Pandemi">
            <label for="alasan">Alasan Membutuhkan Bantuan</label>
              <select v-model="alasan" name="alasan" id="alasan">
                <option value="Kehilangan pekerjaan">Kehilangan pekerjaan</option>
                <option value="Kepala keluarga terdampak atau korban Covid-19">Kepala keluarga terdampak atau korban Covid-19</option>
                <option value="Tergolong fakir/miskin semenjak sebelum Covid-19">Tergolong fakir/miskin semenjak sebelum Covid-19</option>
                <option value="Lainnya">Lainnya...</option>
              </select>
            <div v-if="alasan === 'Lainnya'">
            <input type="text" name="alasan" v-model="alsan_lainnya" placeholder="Alasan Lainnya"> 
            </div>            
            <input type="file" accept="image/png" @change=uploadKTP>
            <input type="file" accept="image/png" @change=uploadKK>
            <input type="checkbox" value="Saya menyatakan bahwa data yang diisikan adalah benar dan siap mempertanggungjawabkan apabila ditemukan ketidaksesuaian dalam data tersebut." v-model="checked">
            <label>Saya menyatakan bahwa data yang diisikan adalah benar dan siap mempertanggungjawabkan apabila ditemukan ketidaksesuaian dalam data tersebut.</label>
            <input type="submit" value="Submit" class="btn btn-info">
        </form> -->
</div>
</template>

<script>
export default {
       name: "AddUserItem",
        data () {
            return {
                errors:[],
                nik: '',
                no_kk: '',
                umur: '',
                jk: '',
                provinsi: '',
                kabkota: '',
                kec: '',
                keldes: '',
                alamat:'',
                rt: '',
                rw: '',
                p_before: '',
                p_after: '',
                alasan: '',
                nama: '',
                previewKTP:'',
                previewKK:'',
                checked: '',
                id: '',
            }
        },
        methods: {
          uploadKTP(e){
                const image = e.target.files[0];
                const reader = new FileReader();
                reader.readAsDataURL(image);
                reader.onload = e =>{
                    this.previewKTP = e.target.result;
                    // console.log(this.previewImage);
                };
          },
          uploadKK(e){
                const image = e.target.files[0];
                const reader = new FileReader();
                reader.readAsDataURL(image);
                reader.onload = e =>{
                    this.previewKK = e.target.result;
                    // console.log(this.previewImage);
                };
          },
            addUser(e){
                    const newUser = {
                        nama: this.nama,
                        nik: this.nik,
                        no_kk: this.no_kk,
                        umur: this.umur,
                        jk: this.jk,
                        provinsi: this.provinsi,
                        kabkota: this.kabkota,
                        kec: this.kec,
                        keldes: this.keldes,
                        alamat: this.alamat,
                        rt: this.rt,
                        rw: this.rw,
                        p_before: this.p_before,
                        p_after: this.p_after,
                        alasan: this.alasan,
                        previewKTP: this.previewKTP,
                        previewKK: this.previewKK,
                        checked: this.checked,
                        id: Math.floor(Math.random() * 100)
                    };
                    if (newUser.nama !== '' && newUser.nik !== '' && newUser.no_kk !== '' && newUser.previewKTP !== '' && newUser.previewKK && newUser.checked !== '' && newUser.jk !== '' && newUser.provinsi !== '' && newUser.kabkota !== '' && newUser.kec !== '' && newUser.keldes !== '' && newUser.rt !== '' && newUser.rw !== '' && newUser.p_before !== '' && newUser.p_after !== '' && newUser.alasan !== '' && newUser.umur !== '' && newUser.alamat !== ''){
                        this.$router.push("/user");
                        this.$emit('add-user-event', newUser);
                    }
                this.errors = [];

                if (!this.nama) {
                  this.errors.push('Name required.');
                }
                if (!this.nik) {
                  this.errors.push('NIK required.');
                }
                if (!this.no_kk) {
                  this.errors.push('No KK required.');
                }
                if (!this.umur) {
                  this.errors.push('Umur required.');
                }
                if (!this.jk) {
                  this.errors.push('Jenis Kelamin required.');
                }
                if (!this.provinsi) {
                  this.errors.push('Provinsi required.');
                }
                if (!this.kabkota) {
                  this.errors.push('Kabupaten / Kota required.');
                }
                if (!this.kec) {
                  this.errors.push('Kecamatan required.');
                }
                if (!this.keldes) {
                  this.errors.push('Keldes required.');
                }
                if (!this.alamat) {
                  this.errors.push('Alamat required.');
                }
                if (!this.rt) {
                  this.errors.push('RT required.');
                }
                if (!this.rw) {
                  this.errors.push('RW required.');
                }
                if (!this.p_before) {
                  this.errors.push('Penghasilan Sebelum required.');
                }
                if (!this.p_after) {
                  this.errors.push('Penghasilan Sesudah required.');
                }
                if (!this.alasan) {
                  this.errors.push('Penghasilan Sesudah required.');
                }
                if (!this.previewKTP) {
                  this.errors.push('KTP required.');
                }    
                if (!this.previewKK) {
                  this.errors.push('KK required.');
                }    
                if (!this.checked) {
                  this.errors.push('check required.');
                }    
                e.preventDefault();
            }
        },
}
</script>

<style scoped>
.login-form {
  padding: 2em;
  border: 1px solid #a8a8a8;
  border-radius: .5em;
  max-width: 500px;
  box-sizing: border-box;
}
.form-title {
  margin-top: 0;
}
.login-form::v-deep .formulate-input .formulate-input-element {
  max-width: none;
}
@media (min-width: 420px) {
  .double-wide {
    display: flex;
  }
  .double-wide .formulate-input {
    flex-grow: 1;
    width: calc(50% - .5em);
  }
  .double-wide .formulate-input:first-child {
    margin-right: .5em;
  }
  .double-wide .formulate-input:last-child {
    margin-left: .5em;
  }
}
</style>