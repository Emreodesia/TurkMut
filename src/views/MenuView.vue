<template>
    <div class="main">
        <div class="background-design">
            <img :src="backgroundImage" alt="" />
        </div>
        <div class="main-text">
            <div class="main-body">
                <p><span class="yellow">Menümüz </span>____________</p>
                <p class="main-2">
                    Keşfedin <br />
                    Menümüzü
                </p>
            </div>
            <h2>Başlangıçlar</h2>
            <h3>Vejetaryen</h3>
            <div class="menu-grid">
                <MenuCard :imgPath="springRoll" imgTitle="Mercimek Çorbası" />
                <MenuCard :imgPath="haraBharaKabab" imgTitle="Humus" />
                <MenuCard :imgPath="paneerTikka" imgTitle="Patlıcan Ezme" />
                <MenuCard :imgPath="dahiBhallaChaat" imgTitle="Cacık" />
                <MenuCard :imgPath="vegMomos" imgTitle="Dolma" />
            </div>
            <h3>Etli</h3>
            <div class="menu-grid">
                <MenuCard :imgPath="chilliPrawns" imgTitle="Karides Güveç" />
                <MenuCard :imgPath="chickenManchurian" imgTitle="Tavuk Şiş" />
                <MenuCard :imgPath="seekhKebab" imgTitle="Adana Kebap" />
                <MenuCard :imgPath="muttonVadai" imgTitle="Kuzu Pirzola" />
                <MenuCard :imgPath="periPeriFishFingers" imgTitle="Balık Izgara" />
            </div>
            <h2>Ana Yemekler</h2>
            <h3>Vejetaryen</h3>
            <div class="menu-grid">
                <MenuCard :imgPath="paneerGravy" imgTitle="Mantı" />
                <MenuCard :imgPath="masalaDosa" imgTitle="Gözleme" />
                <MenuCard :imgPath="southMeals" imgTitle="Pide" />
                <MenuCard :imgPath="northMeals" imgTitle="Lahmacun" />
                <MenuCard :imgPath="idliVada" imgTitle="Börek" />
            </div>
            <h3>Etli</h3>
            <div class="menu-grid">
                <MenuCard :imgPath="butterChicken" imgTitle="İskender Kebap" />
                <MenuCard :imgPath="laalMaas" imgTitle="Urfa Kebap" />
                <MenuCard :imgPath="fishCurry" imgTitle="Hamsi Tava" />
                <MenuCard :imgPath="biryani" imgTitle="Pilav" />
                <MenuCard :imgPath="chickenChettinad" imgTitle="Tavuk Sote" />
            </div>
            <h2>Tatlılar</h2>
            <div class="menu-grid">
                <MenuCard :imgPath="gulabJamun" imgTitle="Baklava" />
                <MenuCard :imgPath="rasmalai" imgTitle="Künefe" />
                <MenuCard :imgPath="gajarKaHalwa" imgTitle="Kemalpaşa" />
                <MenuCard :imgPath="malaiKiKheer" imgTitle="Sütlaç" />
                <MenuCard :imgPath="mishtiDoi" imgTitle="Aşure" />
            </div>
        </div>
    </div>
    <Footer />
</template>

<script setup>
import MenuCard from '@/components/MenuCard.vue';
import Footer from '@/components/Footer.vue';

import backgroundImage from '@/assets/images/new_background.svg';
import springRoll from '@/assets/images/spring role.jpg';
import haraBharaKabab from '@/assets/images/hara bhara kabab.jpg';
import paneerTikka from '@/assets/images/panner tikka.jpg';
import dahiBhallaChaat from '@/assets/images/dahi bhalla chaat.jpg';
import vegMomos from '@/assets/images/momos.jpg';
import chilliPrawns from '@/assets/images/chilli prawns.jpg';
import chickenManchurian from '@/assets/images/chicken manchurian.jpg';
import seekhKebab from '@/assets/images/seekh kebab.jpg';
import muttonVadai from '@/assets/images/mutton vadai.jpg';
import periPeriFishFingers from '@/assets/images/peri peri fish fingers.jpg';
import paneerGravy from '@/assets/images/panner gravy and naan.jpg';
import masalaDosa from '@/assets/images/masala dosa.jpg';
import southMeals from '@/assets/images/south meals.jpg';
import northMeals from '@/assets/images/north meals.jpg';
import idliVada from '@/assets/images/idli vada.jpg';
import butterChicken from '@/assets/images/butter chicken.jpg';
import laalMaas from '@/assets/images/rajasthani laal maas.jpg';
import fishCurry from '@/assets/images/fish curry.jpg';
import biryani from '@/assets/images/hyderabadi biryani.jpg';
import chickenChettinad from '@/assets/images/chicken chettinad.jpg';
import gulabJamun from '@/assets/images/gulab jamun.jpg';
import rasmalai from '@/assets/images/rasmalai.jpg';
import gajarKaHalwa from '@/assets/images/gajar ka halwa.jpg';
import malaiKiKheer from '@/assets/images/malai ki kheer.jpg';
import mishtiDoi from '@/assets/images/mishti-doi.jpg';
</script>


<style lang="css" scoped>
.menu-icon {
    display: block;
    font-size: 28px;
    cursor: pointer;
    margin-right: -4rem;
}


.background-design img {
    height: 70dvh;
    opacity: 50%;
}

.main {
    margin-top: 5vh;
    margin-bottom: 10vh;
    display: flex;
    gap: 10vw;
    font-size: 2rem;
    color: white;
}

.yellow {
    color: var(--secondary-color);
}

.main-2 {
    margin-top: 4vh;
    font-size: 3.5rem;
    font-family: 'Playfair Display', serif;
}

.menu-grid {
    margin-top: 1vh;
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start;
}

.main-text h2 {
    margin-top: 2vh;
    font-size: 3rem;
    font-weight: normal;
    font-family: 'Playfair Display', serif;
}

.main-text h3 {
    font-size: 2rem;
    font-weight: normal;
}
</style>