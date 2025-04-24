<template>
  <div
    class="relative h-screen w-screen bg-[#252627] bg-[url('/bg-img/WebBG.png')]"
  >
    <div
      class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 bg-white w-full h-70"
    > 
    <!-- Büyük ekranda görünüm -->
      <div
        class="hidden lg:flex absolute drop-shadow-2xl/80 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 z-10 overflow-hidden h-165 rounded-4xl "
      >
        <div
          class="w-150 col-span-2 drop-shadow-xl/50 flex items-center justify-end rounded-l-4xl bg-gradient-to-r from-[#5929B9] to-[#8c33ef]"
        >
          <div class="flex items-center justify-between">
            <div class="text-white flex flex-col gap-6">
              <h2 class="text-5xl tracking-widest px-8 leading-15">
                Küreselleşin <br />
                Daha Akıllıca <br />
                Satış Yapın
              </h2>

              <p class="px-8">
                Hiçbir kayıt ücreti ödemeden dünya çapında milyonlarca
                kullanıcıya ulaşın.
              </p>
            </div>

            <NuxtImg src="Login/women.png" class="object-contain max-h-150" />
          </div>
        </div>
        <div class="w-115 rounded-r-4xl bg-white">
          <div
            class="bg-gradient-to-r from-[#5929B9] to-[#8c33ef] w-55 mt-3 text-white px-4 py-4 rounded-r-4xl tracking-widest"
          >
            <h2>Tekrar hoş geldiniz!</h2>
          </div>
          <div class="flex flex-col gap-14 mt-18 px-10 text-[#06475d]">
            <h2 class="font-extrabold text-xl tracking-wider">Hesabına Giriş Yap</h2>

            <div class="relative">
              <input
                type="text"
                placeholder="E-posta"
                class="w-full pb-2 bg-transparent outline-none"
              />
              <div
                class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
              ></div>
            </div>
            <div class="relative">
              <input
                :type="showPassword ? 'text' : 'password'"
                placeholder="Şifre"
                class="w-full pb-2 bg-transparent outline-none pr-10"
              />
              <button
                type="button"
                @click="togglePassword"
                class="absolute right-0 top-1/2 -translate-y-1/2 pr-2 text-gray-500"
              >
                <Icon
                  :name="showPassword ? 'mdi:eye-off' : 'mdi:eye'"
                  class="text-xl"
                />
              </button>
              <div
                class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
              ></div>
              <div class="flex absolute my-3">
                <input
                  type="checkbox"
                  v-model="rememberMe"
                  id="remember"
                  class="h-4 w-4 accent-[#1C3E7E]"
                />
                <label for="remember" class="ml-2 text-sm">Beni Hatırla</label>
              </div>
            </div>
            <div class="flex-center flex-col gap-3">
              <NuxtLink>
                <button
                  class="bg-gradient-to-r from-[#5929B9] to-[#8c33ef] rounded-full text-white text-xl py-3 w-35"
                >
                  Giriş Yap
                </button>
              </NuxtLink>
              <NuxtLink to="/SellerRegister">
                <h2 class="font-medium">Hesap Oluştur</h2>
              </NuxtLink>

              <div class="grid grid-cols-2 gap-2 text-sm">
                <div
                  v-for="(i, index) in accounts"
                  :key="index"
                  class="border border-gray-300 rounded-xl flex items-center py-2 px-3 gap-1"
                >
                  <Icon :name="i.icon" class="text-lg" />
                  <p class="text-gray-700">{{ i.text }}</p>
                </div>
              </div>
              <div class="relative mt-4">
                <h2 class="font-medium mb-1 tracking-wider">Şifremi Unuttum</h2>
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                ></div>
              </div>
            </div>
          </div>
        </div>
      </div>

<!-- Küçük ekranda görünüm -->

<div class="flex lg:hidden justify-end absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 drop-shadow-2xl/80 bg-black overflow-hidden w-[90%] max-w-md h-165 rounded-4xl">
  <NuxtImg
          src="Login/women.png"
          class="h-full object-cover grayscale opacity-20 "
        />
        <div
        class="z-10 lg:relative absolute lg:translate-x-0 left-1/2 -translate-x-1/2 lg:left-auto top-0 w-full lg:w-auto"
      >
        <div
          class="bg-gradient-to-r from-[#5929B9] to-[#8c33ef] w-55 mt-3 text-white px-4 py-4 rounded-r-4xl tracking-widest"
        >
          <h2>Tekrar hoş geldiniz!</h2>
        </div>
        <div
          class="flex flex-col gap-14 mt-18 px-6 sm:px-10 text-white lg:text-[#06475d]"
        >
          <h2 class="font-extrabold text-xl tracking-wider">
            Hesabına Giriş Yap
          </h2>

          <div class="relative">
            <input
              type="text"
              placeholder="E-posta"
              class="w-full pb-2 outline-none bg-transparent text-white lg:text-[#06475d]"
            />
            <div
              class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
            ></div>
          </div>
          <div class="relative">
            <input
              :type="showPassword ? 'text' : 'password'"
              placeholder="Şifre"
              class="w-full pb-2 bg-transparent outline-none pr-10"
            />
            <button
              type="button"
              @click="togglePassword"
              class="absolute right-0 top-1/2 -translate-y-1/2 pr-2 text-gray-500"
            >
              <Icon
                :name="showPassword ? 'mdi:eye-off' : 'mdi:eye'"
                class="text-xl"
              />
            </button>
            <div
              class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
            ></div>
            <div class="flex absolute my-3">
              <input
                type="checkbox"
                v-model="rememberMe"
                id="remember"
                class="h-4 w-4 accent-[#1C3E7E]"
              />
              <label for="remember" class="ml-2 text-sm"
                >Beni Hatırla</label
              >
            </div>
          </div>

          <div class="flex-center flex-col gap-3">
            <NuxtLink>
              <button
                class="bg-gradient-to-r from-[#5929B9] to-[#8c33ef] rounded-full text-white text-xl py-3 w-35"
              >
                Giriş Yap
              </button>
            </NuxtLink>
            <NuxtLink to="/">
              <h2 class="font-medium">Hesap Oluştur</h2>
            </NuxtLink>
            <div class="grid grid-cols-2 gap-2 text-[0.6rem] sm:text-sm">
              <div
                v-for="(i, index) in accounts"
                :key="index"
                class="border border-gray-300 rounded-xl flex items-center py-2 px-2 gap-1 bg-gray-100 lg:bg-white"
              >
                <Icon :name="i.icon" class="text-lg text-gray-700" />
                <p class="text-gray-700">{{ i.text }}</p>
              </div>
            </div>
            <div class="relative mt-4">
              <h2 class="font-medium mb-1 tracking-wider">
                Şifremi Unuttum
              </h2>
              <div
                class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
              ></div>
            </div>
          </div>
        </div>
      </div>
 </div>
    </div>
  </div>
</template>

<script setup>
const rememberMe = ref(false);
const showPassword = ref(false);
const togglePassword = () => {
  showPassword.value = !showPassword.value;
};
const accounts = [
  { icon: "fa-brands:facebook-f", text: "Facebook ile devam et" },
  { icon: "pajamas:twitter", text: "Twitter ile devam et" },
  { icon: "devicon:google", text: "Google ile devam et" },
  { icon: "logos:paypal", text: "Paypal ile devam et" },
];
</script>




