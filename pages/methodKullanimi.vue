<template>
  <div class="m-5">
    <h1 class="font-semibold text-2xl">{{ title }}</h1>
    {{ titleLengthMessage }}
    <!-- computed kullanmak için ekledik  -->
    <input type="text" class="border rounded-2xl p-2 m-2" v-model="title" />
    <button class="border rounded-2xl p-2" @click="tikla">Tıkla</button>
    <p v-if="show">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio quos
      voluptates omnis, expedita delectus consectetur repellat et atque quisquam
      ea nam earum vel. Et veniam delectus neque at eligendi commodi!
    </p>
    <hr />
    <button @click="counter++" class="border p-2 rounded-2xl my-3 bg-pink-300">
      {{ counter }} - {{ tekCift }}
    </button>

    <hr>
    <input type="text" v-model="searchText" class="border rounded-2xl p-2 m-2">
    <p v-if="isTyping">Şuan yazıyor...</p>
  </div>
</template>

<script setup>
const title = ref("bu bir başlık..");
const show = ref(false);
const tikla = () => {
  //fonskiyon tanımlama
  show.value = !show.value; // sadece show= !show yazdığımızda çalışmıyor neden??
};

// computed kullanımı: fonksiyon gibi çalışan değişkenler 
// Başka bir değişkene bağlı olarak otomatik yeniden hesaplanan bir değer üretir.
const titleLengthMessage = computed(() => {
  return title.value.length + " adet karakter yazdınız.";
});

// // tek satırlık veri ise return kullanmadan bu şekilde de yazılabilir
// const titleLengthMessage = computed(()=> title.value.length + " adet karakter yazdınız")



//******************************************************************************************************************************
// Computed: Başka bir değişkene bağlı olarak otomatik yeniden hesaplanan bir değer üretir.
const counter = ref(0);
const tekCift = computed(() => counter.value % 2 === 0? 'Çift' : 'Tek'); // counterın içindeki değerin 2'ye bölümünden kalan 0'sa çift yazdır değilse tek yaz
watch([counter, tekCift],(newValue, oldValue)=>{  //tek yapı incelenecekse bu şekilde  watch(counter,(newValue, oldValue)
  console.log("Eski Değer:", oldValue, "Yeni Değer:",newValue );
})
//******************************************************************************************************************************


//watch ve watchEffect kullanımı 
const searchText=ref();
const isTyping=ref(false);

watch(searchText, ()=>{   //watch kullandığımızda yazmaya başlayınca yazıyor.. çıkıyor ama yazmayı buraktığımızda hala yazıyor.. yazısı gözüküyor bunun için setTimeout kullanıyoruz
  if(searchText.value.length > 0){
    isTyping.value = true;
  }

  setTimeout(()=>{  //1,5 saniye sonra yazı kapanıyor ama yazmaya devam ettiğimizde yazıyor.. yazısı göz kırpıyor bu iyi bir görüntü değil bu yüzden watchEffect kullanıyoruz
    isTyping.value=false;
  },1500);
  
});

///watchEffect
watchEffect((onInvalidate)=>{
   if(searchText.value.length > 0){
    isTyping.value=true;

    const typing=setTimeout(()=>{
      isTyping.value=false;
    },1500)
  
  onInvalidate(()=>clearTimeout(typing));
  }
});
</script>
