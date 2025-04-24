<template>
        <div class="w-full h-full">
          <HeaderAccountBarMenu  />
          <div class="mt-3" >
          <HeaderDropDownMenuComp
        
          class="border-t  border-gray-300 py-3 text-white bg-gray-500"
          v-for="(i, index) in DropDownMenu"
          :key="index"
          :id="i.id"
          :name="i.name"
          :point="i.point"
          :AccountId="i.AccountId"
          :url="i.url"
          :img="i.img"
          :icon="i.icon"
        /></div>
       
        </div>
</template>

<script setup>
const DropDownMenu = [
  {
    id: 1,
    name: "acililahmacun",
    AccountId: "2020469136",
    url: "",
    img: "accountOpenMenu/premium.png",
  },
  {
    id: 2,
    name: "EPINPAY STORE CREDIT",
    url: "",
    point: 100,
    img: "accountOpenMenu/star.png",
  },
  {
    id: 3,
    name: "EPINPAY POINT",
    url: "",
    point: 100,
    img: "accountOpenMenu/smile.png",
  },
  {
    id: 4,
    name: "INVITE FRIENDS & START EARING!",
    url: "",
    img: "accountOpenMenu/accountImg.png",
  },
  { id: 5, name: "OVERVIEW", url: "", icon: "mingcute:down-fill" },
  { id: 6, name: "PURCHASE ORDERS", url: "" },
  { id: 7, name: "SELLING", url: "" },
  { id: 8, name: "EPINPAY AFFILIATE PROGRAM", url: "" },
  {
    id: 9,
    name: "SETTINGS",
    url: "",
    img: "accountOpenMenu/settings.png",
  },
  { id: 10, name: "LOG OUT", url: "", img: "accountOpenMenu/logout.png" },
];
</script>