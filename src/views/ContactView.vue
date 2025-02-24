<template>
  <div class="container mx-auto p-3 md:p-8">
    <div class="flex flex-col-reverse md:flex-row relative">
      <div class="w-full md:w-2/3">
        <div class="flex flex-col gap-4 md:px-20 fade-zoom-up">
          <h1 class="text-2xl font-bold text-white">Contact Me</h1>
          <form @submit.prevent="sendMessage" class="bg-[#1e1e1f] p-5 rounded-xl text-white">
            <div class="mb-4">
              <label class="block text-sm mb-1">Nama</label>
              <input type="text" v-model="form.name" class="w-full p-2 rounded bg-[#282828] border border-[#383838] text-white" required>
            </div>
            <div class="mb-4">
              <label class="block text-sm mb-1">Email</label>
              <input type="email" v-model="form.email" class="w-full p-2 rounded bg-[#282828] border border-[#383838] text-white" required>
            </div>
            <div class="mb-4">
              <label class="block text-sm mb-1">Pesan</label>
              <textarea v-model="form.message" class="w-full p-2 rounded bg-[#282828] border border-[#383838] text-white" required></textarea>
            </div>
            <button type="submit" class="bg-amber-200 text-black px-4 py-2 rounded">Kirim</button>
          </form>
        </div>
      </div>
      <div class="w-full md:w-1/3 h-fit p-8 md:sticky md:top-24">
        <!-- Sidebar -->
        <div class="flex flex-col text-left text-white">
          <div class="bg-clip-text bg-gradient-to-r from-slate-100 to-amber-300 text-transparent text-xl font-semibold">Follow Me</div>
          <div class="h-[1px] mt-4 mb-4 w-20 bg-amber-200"></div>
          <div class="flex flex-col gap-2">
            <a href="https://www.instagram.com/ptrijntaa" target="_blank" class="text-sm text-white hover:text-amber-200">📸 Instagram: ptrijntaa</a>
            <a href="mailto:putrijunita761@gmail.com" class="text-sm text-white hover:text-amber-200">📩 Email: putrijunita761@gmail.com</a>
            <a href="https://wa.me/6289638974608" target="_blank" class="text-sm text-white hover:text-amber-200">📞 WhatsApp: 0896-3897-4608</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      }
    };
  },
  methods: {
    sendMessage() {
      alert(`Pesan dari ${this.form.name} telah dikirim!`);
      this.form.name = '';
      this.form.email = '';
      this.form.message = '';
    }
  }
};
</script>

<style scoped>
/* Animasi fade zoom */
@keyframes fadeZoomUp {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}
.fade-zoom-up {
  animation: fadeZoomUp 1s ease-in-out;
}
</style>
