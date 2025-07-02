<template>
    <main>
        <div class="heading">
            <img :src="logo" alt="logo" />
            <h1>Rezervasyon Yapın</h1>
        </div>
        <form @submit.prevent="validateForm">
            <div class="form1">
                <label for="name">
                    <input type="text" v-model="name" id="name" placeholder="Ad Soyad" required />
                </label>
                <label for="number">
                    <input type="text" v-model="phoneNumber" id="number" placeholder="Telefon Numarası" required
                        pattern="[0-9]{10}" />
                </label>
                <label for="email">
                    <input type="email" v-model="email" id="email" placeholder="E-posta" required />
                </label>
                <label for="guests">
                    <input type="number" v-model="guests" id="guests" placeholder="Kişi Sayısı" required min="1"
                        max="25" />
                </label>
                <label for="date">
                    <input type="date" v-model="date" id="date" placeholder="Rezervasyon Tarihi" required />
                </label>
                <label for="meal-type">
                    <select v-model="mealType" id="meal-type" required>
                        <option selected disabled>Öğün Türü</option>
                        <option value="breakfast">Kahvaltı (08:00 - 10:30)</option>
                        <option value="lunch">Öğle Yemeği (12:00 - 15:30)</option>
                        <option value="dinner">Akşam Yemeği (19:00 - 22:00)</option>
                    </select>
                </label>
                <label for="addinfo">
                    <textarea v-model="additionalInfo" id="addinfo" cols="30" rows="10"
                        placeholder="Ek Bilgiler"></textarea>
                </label>
            </div>
            <div class="form2">
                <div class="valid-container">
                    <span>{{ num1 }}</span>
                    <span id="operation">+</span>
                    <span>{{ num2 }}</span>
                    <span class="equals">=</span>
                    <input v-model="answer" id="ans" type="text" />
                </div>
                <button id="submit" type="submit">Gönder</button>
            </div>
        </form>
    </main>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import logo from '@/assets/images/form-logo.svg'; // Adjust path as needed
const name = ref('');
const phoneNumber = ref('');
const email = ref('');
const guests = ref(1);
const date = ref('');
const mealType = ref('');
const additionalInfo = ref('');
const answer = ref('');
const num1 = ref(0);
const num2 = ref(0);
const sum = ref(0);

const validate = () => {
    num1.value = Math.floor(Math.random() * 10);
    num2.value = Math.floor(Math.random() * 10);
    sum.value = num1.value + num2.value;
}

onMounted(() => {
    validate();
});

const validateForm = () => {
    const userSum = parseInt(answer.value);
    if (sum.value === userSum) {
        alert('Teşekkürler! Rezervasyonunuz başarıyla alındı!');
        name.value = '';
        phoneNumber.value = '';
        email.value = '';
        guests.value = 1;
        date.value = '';
        mealType.value = '';
        additionalInfo.value = '';
        answer.value = '';
        validate();

    } else {
        alert('Hatalı! Tekrar deneyin');
    }
};

</script>

<style scoped>
main {
    background-image: linear-gradient(rgba(227, 10, 23, 0.1), rgba(227, 10, 23, 0.8), #E30A17),
        url('@/assets/images/form-background.jpg');
    background-repeat: no-repeat;
    background-size: cover;
}

main,
.heading {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.heading h1 {
    font-size: 2.5rem;
    font-weight: normal;
    color: white;
    font-family: 'Playfair Display', serif;
}

form {
    width: 70vw !important;
    max-width: 700px;
}

.form1 {
    display: flex;
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
}

.form2 {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 1em;
}

form input,
select {
    width: 20vw;
    min-width: 200px;
    margin: 1vh 0.5vw;
    padding: 10px;
    border: none;
}

input::placeholder {
    color: black;
}

select option {
    font-size: 1.2rem;
}

#meal-type {
    width: 21.5vw;
}

input:focus,
textarea:focus,
select:focus {
    outline: 3px solid var(--secondary-color);
    border: none;
}

textarea {
    float: left;
    min-width: 200px;
    width: 43vw;
    height: 60px;
    max-width: 43vw;
    margin: 1vh 0.5vw;
    padding: 10px;
}

#submit {
    background-color: var(--secondary-color);
    color: var(--primary-color);
    border: none;
    border-radius: 10px;
    font-size: 1.3rem;
    width: 300px;
    height: 60px;
    margin: 1em 0;
}

#submit:hover {
    transform: scale(1.1);
}

.valid-container input {
    width: 10px;
    height: 30px;
    margin-left: 10px;
    font-size: 2rem;
}
span{
    color: white;
}
.valid-container {
    font-family: Arial, Helvetica, sans-serif;
    font-size: 2rem;
    display: flex;
    align-items: center;
    filter: blur(0.6px);
}
</style>