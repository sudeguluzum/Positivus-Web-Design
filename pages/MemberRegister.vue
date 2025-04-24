<template>
  <div
    class="relative h-screen w-screen bg-[#252627] bg-[url('/bg-img/WebBG.png')]"
  >
    <div
      class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 bg-white w-full h-70"
    >
      <!-- Büyük ekranda görünüm -->
      <div
        class="hidden lg:flex absolute drop-shadow-2xl/80 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 z-10 overflow-hidden h-auto rounded-4xl"
      >
        <div
          class="w-150 col-span-2 drop-shadow-xl/50 flex items-center justify-end rounded-l-4xl"
        >
          <NuxtImg src="Login/login-1.png" class="h-full w-full object-cover" />
        </div>
        <div class="w-115 rounded-r-4xl py-6 bg-white">
          <div
            class="bg-gradient-to-r from-[#1C3E7E] to-[#1b9a88] w-55  text-white px-10 py-4 rounded-r-4xl font-bold text-xl tracking-widest"
          >
            <h2>Kayıt Ol</h2>
          </div>
          <div class="flex flex-col gap-7 mt-10 px-10 text-[#06475d]">
            <div class="grid grid-cols-2 gap-4">
              <div class="relative">
                <input
                  type="text"
                  placeholder="Ad"
                  class="w-full pb-2 bg-transparent outline-none"
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
                ></div>
              </div>
              <div class="relative">
                <input
                  type="text"
                  placeholder="Soyad"
                  class="w-full pb-2 bg-transparent outline-none"
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
                ></div>
              </div>
            </div>
            <div class="relative">
              <input
                type="text"
                placeholder="E-posta"
                class="w-full pb-2 bg-transparent outline-none"
              />
              <div
                class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
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
                class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
              ></div>
            </div>
            <div class="relative">
              <input
                :type="showPassword ? 'text' : 'password'"
                placeholder="Şifre tekrar"
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
                class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
              ></div>
            </div>
            <div class="flex-center flex-col gap-5">
              <NuxtLink>
                <button
                  class="bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] rounded-full text-white text-xl py-3 w-35"
                >
                  Kayıt Ol
                </button>
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
                <NuxtLink to="/MemberLogin">
                  <h2 class="font-medium mb-1 tracking-wider">
                    Hesabın var mı? Giriş yap
                  </h2>
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
                  ></div>
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Küçük ekranda görünüm -->

      <div
        class="flex lg:hidden absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 drop-shadow-2xl/80 bg-black overflow-hidden w-[90%] max-w-md h-152 rounded-4xl"
      >
        <NuxtImg
          src="Login/login.png"
          class="object-cover grayscale opacity-20"
        />
        <div
          class="py-6 z-10 lg:relative absolute lg:translate-x-0 left-1/2 -translate-x-1/2 lg:left-auto top-0 w-full lg:w-auto"
        >
        <div
            class="bg-gradient-to-r from-[#1C3E7E] to-[#1b9a88] w-55  text-white px-10 py-4 rounded-r-4xl font-bold text-xl tracking-widest"
          >
            <h2>Kayıt Ol</h2>
          </div>
          <div class="flex flex-col gap-7 mt-10 px-10 text-[#06475d]">
            <div class="grid grid-cols-2 gap-4">
              <div class="relative">
                <input
                  type="text"
                  placeholder="Ad"
                  class="w-full pb-2 outline-none bg-transparent text-white "
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
                ></div>
              </div>
              <div class="relative">
                <input
                  type="text"
                  placeholder="Soyad"
                  class="w-full pb-2 bg-transparent outline-none text-white"
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
                ></div>
              </div>
            </div>
            <div class="relative">
              <input
                type="text"
                placeholder="E-posta"
                class="w-full pb-2 bg-transparent outline-none text-white"
              />
              <div
                class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
              ></div>
            </div>

            <div class="relative">
              <input
                :type="showPassword ? 'text' : 'password'"
                placeholder="Şifre"
                class="w-full pb-2 bg-transparent outline-none pr-10 text-white"
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
                class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
              ></div>
            </div>
            <div class="relative">
              <input
                :type="showPassword ? 'text' : 'password'"
                placeholder="Şifre tekrar"
                class="w-full pb-2 bg-transparent outline-none pr-10 text-white"
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
                class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
              ></div>
            </div>
            <div class="flex-center flex-col gap-5">
              <NuxtLink>
                <button
                  class="bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] rounded-full text-white text-xl py-3 w-35"
                >
                  Kayıt Ol
                </button>
              </NuxtLink>

              <div class="grid grid-cols-2 gap-2 text-[0.6rem] sm:text-sm ">
              <div
                v-for="(i, index) in accounts"
                :key="index"
                class="border border-gray-300 rounded-xl flex items-center py-2 px-2 gap-1 bg-gray-100 lg:bg-white "
              >
                <Icon :name="i.icon" class="text-lg text-gray-700" />
                <p class="text-gray-700">{{ i.text }}</p>
              </div>
            </div>
              <div class="relative mt-4">
                <NuxtLink to="/MemberLogin">
                  <h2 class="font-medium mb-1 tracking-wider text-white">
                    Hesabın var mı? Giriş yap
                  </h2>
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
                  ></div>
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
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
