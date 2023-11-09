<script setup>
import { contactText } from "@/constants/index"
</script>

<template>
    <section id="contact">
        <div class="contact__inner">
            <h2 class="contact__title">Contact <em>연락</em></h2>
            <div class="contact__line" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
            <div class="contact__text" v-for="(contact, key) in contactText" :key="key">
                <div class="text">
                    <a :href="contact.link">{{ contact.title }}</a>
                </div>
            </div>
            <div class="contact__line bottom" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
        </div>
    </section>
    <!-- //contact -->
</template>

<style lang="scss">
#contact {
    width: 100%;
    height: 100vh;
}

.contact__inner {
    padding: 16px;
}

.contact__title {

    top: 68px;
    left: 0;
    height: 5vw;
    width: 70%;
    height: 4.9vw;
    font-size: 4vw;
    font-weight: 900;
    line-height: 1.6;
    text-transform: uppercase;
    font-family: var(--mainTitle-font);
    color: var(--mainfont-color);
    border-bottom: 0.3vw solid var(--mainfont-color);
    margin-bottom: 67.5px;
}

.contact__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 400;
    display: inline-block;
}

.contact__line {
    display: block;
    width: 100%;
}

.contact__line .line {
    display: block;
    width: 100%;
    height: 1px;
    background-color: var(--subBg300);
    margin-bottom: 0.5vw;
}

.contact__line .line:nth-child(1) {
    height: 1px;
}

.contact__line .line:nth-child(2) {
    height: 2px;
}

.contact__line .line:nth-child(3) {
    height: 3px;
}

.contact__line .line:nth-child(4) {
    height: 4px;
}

.contact__line .line:nth-child(5) {
    height: 5px;
}

.contact__line .line:nth-child(6) {
    height: 6px;
}

.contact__line .line:nth-child(7) {
    height: 7px;
}

.contact__line.bottom {
    display: none;
}

.contact__line.bottom .line:nth-child(1) {
    height: 7px;
}

.contact__line.bottom .line:nth-child(2) {
    height: 6px;
}

.contact__line.bottom .line:nth-child(3) {
    height: 5px;
}

.contact__line.bottom .line:nth-child(4) {
    height: 4px;
}

.contact__line.bottom .line:nth-child(5) {
    height: 3px;
}

.contact__line.bottom .line:nth-child(6) {
    height: 2px;
}

.contact__line.bottom .line:nth-child(7) {
    height: 1px;
}

.contact__text {
    height: 300px;
    background-color: var(--mainfont-color);
    text-align: center;
    padding: 120px 0;
    font-size: 25px;
    font-weight: bold;
    color: var(--mainBg-color);
}

@media (max-width: 800px) {
    .contact__title {
        width: 100%;
        padding: 10px 0;
        margin-bottom: 10vw;
        height: auto;
        background-color: var(--mainBg-color);
    }

    .contact__line {
        justify-content: center;
    }

    .contact__line.bottom {
        display: block;
    }

    .contact__text {
        height: 200px;
        padding: 90px 0;
        font-size: 15px;
    }
}
</style>