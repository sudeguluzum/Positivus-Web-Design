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
          <div class="w-115 rounded-r-4xl py-6 bg-white">
            <div
              class="bg-gradient-to-r from-[#5929B9] to-[#8c33ef] w-55 text-white font-bold text-xl px-10 py-4 rounded-r-4xl tracking-widest"
            >
              <h2>Satıcı Ol!</h2>
            </div>
            <div
              class="border-y border-gray-300 mt-3 px-16 h-15 grid grid-cols-2 place-items-center"
            >
              <div
                v-for="(i, index) in accounts"
                :key="index"
                class="flex items-center gap-2"
              >
                <div
                  class="w-5 aspect-square rounded-full flex items-center justify-center bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
                >
                  <Icon :name="i.icon" class="text-xl text-white" />
                </div>
                <p class="text-gray-700">{{ i.text }}</p>
              </div>
            </div>
            <div class="flex flex-col gap-7 mt-10 px-10 text-[#06475d]">
              <div class="grid grid-cols-3 gap-4">
                <div class="relative">
                  <input
                    type="text"
                    placeholder="Gün"
                    class="w-full pb-2 bg-transparent outline-none"
                    maxlength="2"
                    @input="
                      (e) =>
                        (e.target.value = e.target.value.replace(/[^0-9]/g, ''))
                    "
                  />
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
                <div class="relative">
                  <div
                    class="w-full flex items-center justify-between pb-2 cursor-pointer"
                    @click="showMonths = !showMonths"
                  >
                    <input
                      type="text"
                      placeholder="Ay"
                      readonly
                      :value="selectedMonth"
                      class="w-full bg-transparent outline-none"
                    />
                    <Icon
                      name="mingcute:down-line"
                      class="text-xl ml-2 text-gray-600"
                    />
                  </div>
  
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
  
                  <ul
                    v-if="showMonths"
                    class="absolute z-10 w-full bg-white border border-gray-300 rounded-md mt-1 max-h-48 overflow-y-auto shadow-lg"
                  >
                    <li
                      v-for="(month, index) in months"
                      :key="index"
                      @click="selectMonth(month)"
                      class="px-4 py-2 hover:bg-purple-100 cursor-pointer"
                    >
                      {{ month }}
                    </li>
                  </ul>
                </div>
                <div class="relative">
                  <input
                    type="text"
                    placeholder="Yıl"
                    class="w-full pb-2 bg-transparent outline-none"
                    maxlength="4"
                    @input="
                      (e) =>
                        (e.target.value = e.target.value.replace(/[^0-9]/g, ''))
                    "
                  />
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
                <div class="col-span-3">
                  <p class="text-[0.6rem] text-gray-400">
                    Lütfen kimlik belgenizle uyumlu doğum tarihinizi giriniz.
                    Epinpay üzerinden satış yapabilmeniz için en az 18 yaşında
                    olmanız gerekmektedir.
                  </p>
                </div>
              </div>
              <div class="relative">
                <input
                  :type="showPassword ? 'text' : 'password'"
                  placeholder="Kimlik No (opsiyonel)"
                  class="w-full pb-2 bg-transparent outline-none pr-10"
                  @input="
                    (e) =>
                      (e.target.value = e.target.value.replace(/[^0-9]/g, ''))
                  "
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
              </div>
  
              <div class="grid grid-cols-[1fr_3fr] gap-4">
                <div class="relative">
                  <div
                    class="w-full flex items-center justify-between pb-2 cursor-pointer"
                    @click="showTax = !showTax"
                  >
                    <Icon :name="selectedTax.icon" class="text-xl px-2" />
                    <input
                      type="text"
                      placeholder="TR"
                      readonly
                      :value="selectedTax.text"
                      class="w-full bg-transparent outline-none px-2"
                    />
                    <Icon
                      name="mingcute:down-line"
                      class="text-xl text-gray-600"
                    />
                  </div>
  
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
  
                  <ul
                    v-if="showTax"
                    class="absolute z-10 w-full bg-white border border-gray-300 rounded-md mt-1 max-h-48 overflow-y-auto shadow-lg"
                  >
                    <li
                      v-for="(tax, index) in taxs"
                      :key="index"
                      @click="selectTax(tax)"
                      class="px-4 py-2 hover:bg-purple-100 cursor-pointer flex items-center gap-2"
                    >
                      <Icon :name="tax.icon" class="text-xl" />
                      {{ tax.text }}
                    </li>
                  </ul>
                </div>
                <div class="relative">
                  <input
                    type="text"
                    placeholder="Vergi kayıt no (opsiyonel)"
                    class="w-full pb-2 bg-transparent outline-none"
                  />
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
              </div>
  
              <div class="relative border-t border-gray-300 mt-8">
                <h2 class="my-8 font-semibold">Fatura Adresi</h2>
                <input
                  type="text"
                  placeholder="Adres 1"
                  class="w-full pb-2 bg-transparent outline-none"
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                ></div>
              </div>
              <div class="relative">
                <input
                  type="text"
                  placeholder="Adres 2"
                  class="w-full pb-2 outline-none bg-transparent text-white lg:text-[#06475d]"
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                ></div>
              </div>
              <div class="relative">
                <input
                  type="text"
                  placeholder="Şehir"
                  class="w-full pb-2 outline-none bg-transparent text-white lg:text-[#06475d]"
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                ></div>
              </div>
              <div class="grid grid-cols-[2fr_1fr] gap-4">
                <div class="relative">
                  <div
                    class="w-full flex items-center justify-between pb-2 cursor-pointer"
                    @click="showState = !showState"
                  >
                    <input
                      type="text"
                      placeholder="Lütfen Seçiniz"
                      readonly
                      :value="selectedState.text"
                      class="w-full bg-transparent outline-none px-2"
                    />
                    <Icon
                      name="mingcute:down-line"
                      class="text-xl text-gray-600"
                    />
                  </div>
  
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
  
                  <DropDownDeneme
      :items="states"
      :show="showState"
      @select="selectState"
    />
                </div>
                <div class="relative">
                  <input
                    type="text"
                    placeholder="Posta Kodu"
                    class="w-full pb-2 bg-transparent outline-none"
                  />
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
              </div>
  
              <div class="flex-center flex-col gap-3">
                <div class="grid grid-cols-2 gap-4">
                  <NuxtLink>
                    <button
                      class="bg-gradient-to-r from-[#B29CD8] to-[#C9AEEB] rounded-full text-white text-xl py-3 w-35"
                    >
                      Daha Sonra
                    </button>
                  </NuxtLink>
                  <NuxtLink>
                    <button
                      class="bg-gradient-to-r from-[#5929B9] to-[#8c33ef] rounded-full text-white text-xl py-3 w-35"
                    >
                      Devam Et
                    </button>
                  </NuxtLink>
                </div>
                <div class="relative mt-4">
                  <NuxtLink to="/SellerLogin">
                    <h2 class="font-medium mb-1 tracking-wider">
                      Hesabın var mı? Giriş yap
                    </h2></NuxtLink
                  >
  
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
                <p class="text-[0.6rem] text-gray-400">
                  Ticari
                  <NuxtLink to="/">
                    <span class="underline">satıcı hesabı </span> </NuxtLink
                  >oluşturun veya işletme hesabı hakkında
                  <NuxtLink to="/">
                    <span class="underline"> daha fazla bilgi </span>
                  </NuxtLink>
                  edinin.
                </p>
              </div>
            </div>
          </div>
        </div>
  
        <!-- Küçük ekranda görünüm -->
  
        <div
          class="flex lg:hidden justify-end absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 drop-shadow-2xl/80 bg-black overflow-hidden w-[90%] max-w-md h-230 rounded-4xl"
        >
          <NuxtImg
            src="Login/women.png"
            class="h-full object-cover grayscale opacity-20"
          />
          <div
            class="z-10 lg:relative absolute lg:translate-x-0 left-1/2 -translate-x-1/2 lg:left-auto top-0 w-full lg:w-auto"
          >
            <div
              class="bg-gradient-to-r from-[#5929B9] to-[#8c33ef] w-55 mt-3 text-white px-4 py-4 rounded-r-4xl tracking-widest"
            >
              <h2>Satıcı Ol!</h2>
            </div>
            <div
              class="border-y border-gray-300 mt-3 px-16 h-15 grid grid-cols-2 place-items-center"
            >
              <div
                v-for="(i, index) in accounts"
                :key="index"
                class="flex items-center gap-2"
              >
                <div
                  class="w-5 aspect-square rounded-full flex items-center justify-center bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
                >
                  <Icon :name="i.icon" class="text-xl text-white" />
                </div>
                <p class="text-white">{{ i.text }}</p>
              </div>
            </div>
            <div class="flex flex-col gap-7 mt-10 px-10 text-white">
              <div class="grid grid-cols-3 gap-4">
                <div class="relative">
                  <input
                    type="text"
                    placeholder="Gün"
                    class="w-full pb-2 bg-transparent outline-none"
                    maxlength="2"
                    @input="
                      (e) =>
                        (e.target.value = e.target.value.replace(/[^0-9]/g, ''))
                    "
                  />
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
                <div class="relative">
                  <div
                    class="w-full flex items-center justify-between pb-2 cursor-pointer"
                    @click="showMonths = !showMonths"
                  >
                    <input
                      type="text"
                      placeholder="Ay"
                      readonly
                      :value="selectedMonth"
                      class="w-full bg-transparent outline-none"
                    />
                    <Icon
                      name="mingcute:down-line"
                      class="text-xl ml-2 text-gray-600"
                    />
                  </div>
  
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
  
                  <ul
                    v-if="showMonths"
                    class="absolute z-10 w-full bg-white border border-gray-300 rounded-md mt-1 max-h-48 overflow-y-auto shadow-lg text-black"
                  >
                    <li
                      v-for="(month, index) in months"
                      :key="index"
                      @click="selectMonth(month)"
                      class="px-4 py-2 hover:bg-purple-100 cursor-pointer"
                    >
                      {{ month }}
                    </li>
                  </ul>
                </div>
                <div class="relative">
                  <input
                    type="text"
                    placeholder="Yıl"
                    class="w-full pb-2 bg-transparent outline-none"
                    maxlength="4"
                    @input="
                      (e) =>
                        (e.target.value = e.target.value.replace(/[^0-9]/g, ''))
                    "
                  />
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
                <div class="col-span-3">
                  <p class="text-[0.6rem] text-gray-400">
                    Lütfen kimlik belgenizle uyumlu doğum tarihinizi giriniz.
                    Epinpay üzerinden satış yapabilmeniz için en az 18 yaşında
                    olmanız gerekmektedir.
                  </p>
                </div>
              </div>
              <div class="relative">
                <input
                  :type="showPassword ? 'text' : 'password'"
                  placeholder="Kimlik No (opsiyonel)"
                  class="w-full pb-2 bg-transparent outline-none pr-10"
                  @input="
                    (e) =>
                      (e.target.value = e.target.value.replace(/[^0-9]/g, ''))
                  "
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
              </div>
  
              <div class="grid grid-cols-[1fr_3fr] gap-4">
                <div class="relative">
                  <div
                    class="w-full flex items-center justify-between pb-2 cursor-pointer"
                    @click="showTax = !showTax"
                  >
                    <Icon :name="selectedTax.icon" class="text-xl px-2" />
                    <input
                      type="text"
                      placeholder="TR"
                      readonly
                      :value="selectedTax.text"
                      class="w-full bg-transparent outline-none px-2"
                    />
                    <Icon
                      name="mingcute:down-line"
                      class="text-xl text-gray-600"
                    />
                  </div>
  
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
  
                  <ul
                    v-if="showTax"
                    class="absolute z-10 w-full bg-white border border-gray-300 rounded-md mt-1 max-h-48 overflow-y-auto shadow-lg"
                  >
                    <li
                      v-for="(tax, index) in taxs"
                      :key="index"
                      @click="selectTax(tax)"
                      class="px-4 py-2 hover:bg-purple-100 cursor-pointer flex items-center gap-2 text-black"
                    >
                      <Icon :name="tax.icon" class="text-xl" />
                      {{ tax.text }}
                    </li>
                  </ul>
                </div>
                <div class="relative">
                  <input
                    type="text"
                    placeholder="Vergi kayıt no (opsiyonel)"
                    class="w-full pb-2 bg-transparent outline-none"
                  />
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
              </div>
  
              <div class="relative border-t border-gray-300 mt-8">
                <h2 class="my-8 font-semibold">Fatura Adresi</h2>
                <input
                  type="text"
                  placeholder="Adres 1"
                  class="w-full pb-2 bg-transparent outline-none"
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                ></div>
              </div>
              <div class="relative">
                <input
                  type="text"
                  placeholder="Adres 2"
                  class="w-full pb-2 outline-none bg-transparent text-white lg:text-[#06475d]"
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                ></div>
              </div>
              <div class="relative">
                <input
                  type="text"
                  placeholder="Şehir"
                  class="w-full pb-2 outline-none bg-transparent text-white lg:text-[#06475d]"
                />
                <div
                  class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                ></div>
              </div>
              <div class="grid grid-cols-[2fr_1fr] gap-4">
                <div class="relative">
                  <div
                    class="w-full flex items-center justify-between pb-2 cursor-pointer"
                    @click="showState = !showState"
                  >
                    <input
                      type="text"
                      placeholder="Lütfen Seçiniz"
                      readonly
                      :value="selectedState.text"
                      class="w-full bg-transparent outline-none px-2"
                    />
                    <Icon
                      name="mingcute:down-line"
                      class="text-xl text-gray-600"
                    />
                  </div>
  
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
  
                  <DropDownDeneme
      :items="states"
      :show="showState"
      @select="selectState"
    />
                </div>
                <div class="relative">
                  <input
                    type="text"
                    placeholder="Posta Kodu"
                    class="w-full pb-2 bg-transparent outline-none"
                  />
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
              </div>
  
              <div class="flex-center flex-col gap-3">
                <div class="grid grid-cols-2 gap-4">
                  <NuxtLink>
                    <button
                      class="bg-gradient-to-r from-[#B29CD8] to-[#C9AEEB] rounded-full text-white text-xl py-3 w-35"
                    >
                      Daha Sonra
                    </button>
                  </NuxtLink>
                  <NuxtLink>
                    <button
                      class="bg-gradient-to-r from-[#5929B9] to-[#8c33ef] rounded-full text-white text-xl py-3 w-35"
                    >
                      Devam Et
                    </button>
                  </NuxtLink>
                </div>
                <div class="relative mt-4">
                  <NuxtLink to="/SellerLogin">
                    <h2 class="font-medium mb-1 tracking-wider">
                      Hesabın var mı? Giriş yap
                    </h2></NuxtLink
                  >
  
                  <div
                    class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
                  ></div>
                </div>
                <p class="text-[0.6rem] text-gray-400">
                  Ticari
                  <NuxtLink to="/">
                    <span class="underline">satıcı hesabı </span> </NuxtLink
                  >oluşturun veya işletme hesabı hakkında
                  <NuxtLink to="/">
                    <span class="underline"> daha fazla bilgi </span>
                  </NuxtLink>
                  edinin.
                </p>
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
    { icon: "mdi:number-1", text: "Profil Bilgileri" },
    { icon: "mdi:number-2", text: "Doğrulama" },
  ];
  
  const showMonths = ref(false);
  const months = [
    "01",
    "02",
    "03",
    "04",
    "05",
    "06",
    "07",
    "08",
    "09",
    "10",
    "11",
    "12",
  ];
  const selectedMonth = ref("");
  
  function selectMonth(month) {
    selectedMonth.value = month;
    showMonths.value = false;
  }
  
  const taxs = [
    { icon: "flag:tr-4x3", text: "TR" },
    { icon: "twemoji:flag-united-states", text: "USA" },
    { icon: "twemoji:flag-canada", text: "CDN" },
  ];
  const selectedTax = ref(taxs[0]);
  const showTax = ref(false);
  
  const selectTax = (tax) => {
    selectedTax.value = tax;
    showTax.value = false;
  };
  
  const selectedState = ref({ icon: '', text: 'Lütfen Seçiniz' });
const showState = ref(false);

const states = [
  { icon: 'flag:tr-4x3', text: 'Türkiye' },
  { icon: 'twemoji:flag-united-states', text: 'ABD' },
  { icon: 'twemoji:flag-germany', text: 'Almanya' }
];

const selectState = (item) => {
  selectedState.value = item;
  showState.value = false;
};
  </script>
  