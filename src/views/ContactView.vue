<template>
    <div class="contact-container">
        <iframe
            src= "https://www.google.com/maps/embed?pb=!1m10!1m8!1m3!1d532.5828233182361!2d28.985941177834658!3d41.0064740008975!3m2!1i1024!2i768!4f13.1!5e0!3m2!1str!2str!4v1751285469327!5m2!1str!2str"
            width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"></iframe>
        <div class="contact">
            <div class="contact-info">
                <p id="address">Türk Mutfağı, Sultanahmet Meydanı, Fatih, İstanbul, Türkiye - 34122 <br>
                </p>
                <a href="tel:+902121234567">Tel : (+90) 212 123 45 67</a><br>
                <a href="mailto:info@turkmutfagi.com">E-posta : info@turkmutfagi.com</a>
            </div>

        </div>
    </div>

</template>

<script setup></script>

<style lang="css" scoped>
.contact-container {
    display: flex;
    flex-wrap: wrap-reverse;
    justify-content: center;
    align-items: center;
    margin-top: 5vh;
}

iframe {
    min-width: 250px;
    min-height: 100px;
}

.contact {
    width: 30vw;
    display: flex;
    flex-direction: column;
    align-items: center;
    font-size: 1.5rem;
    color: white;
}

#address {
    width: 200px;
}

a {
    font-size: 1.4rem;
    color: white;
    font-family: serif;
}
</style>