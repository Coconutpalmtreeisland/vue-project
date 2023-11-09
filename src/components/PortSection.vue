<script setup>
import { portText } from "@/constants/index"
</script>

<template>
    <section id="port">
        <div class="port__inner">
            <div class="port__title">
                portfolio <em>포폴 작업물</em>
            </div>
            <div class="port__wrap">
                <div v-for="(port, key) in portText" :key="key" :class="'port__item p' + (key + 1)">
                    <span class="num">{{ port.num }}.</span>
                    <a :href="port.view">
                        <img :src="port.img" :alt="'포트폴리오' + (key + 1)">
                    </a>
                    <h3 class="title">{{ port.title }}</h3>
                    <p class="desc">{{ port.desc }}</p>
                </div>
            </div>
        </div>
    </section>
    <!-- //port -->
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
    mounted: function () {
        this.scrollAnimaion();
    },
    methods: {
        scrollAnimaion() {
            const horSection = gsap.utils.toArray(".port__item");

            gsap.to(horSection, {
                xPercent: -120 * (horSection.length - 1),
                ease: "none",
                scrollTrigger: {
                    trigger: "#port",
                    start: "top 56px",
                    end: "+=3000",
                    pin: true,
                    scrub: 1,
                    markers: false,
                    invalidateOnRefresh: true,
                    anticipatePin: 1
                }
            })
        }
    }
}
</script>

<style lang="scss">
#port {
    width: 100%;
    overflow: hidden;
}

.port__inner {
    padding: 16px;
}

.port__wrap {
    display: flex;
    flex-wrap: wrap;
    width: 7000px;
}

.port__item {
    width: 500px;
    height: 70vh;
    background-color: var(--subBg100);
    margin-right: 20px;
}

.port__item:nth-child(even) {
    background-color: var(--mainBg-color);
    border: 1px solid var(--subBg500);
}

.port__title {
    position: sticky;
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

.port__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 400;
    display: inline-block;
}

.port__item {
    padding: 40px 30px;
    display: flex;
    flex-direction: column;
}

.port__item .num {
    font-size: 30px;
    font-family: var(--mainNum-font);
    font-weight: bold;
    color: var(--subBg500);
}

.port__item .title {
    text-align: center;
    font-size: 20px;
    font-weight: 500;
    padding: 10px;
    border-bottom: 2px solid var(--subBg500);
    color: var(--subBg500);
}

.port__item .desc {
    font-size: 16px;
    color: var(--subBg500);
    padding: 10px 0;
}

.port__item:nth-child(even) .num,
.port__item:nth-child(even) .title,
.port__item:nth-child(even) .desc {
    color: var(--subBg500);
}

.port__item:nth-child(even) .title {
    border-bottom: 2px solid var(--subBg500);
}

@media (max-width: 800px) {
    .port__title {
        width: 100%;
        padding: 10px 0;
        margin-bottom: 10vw;
        height: auto;
        background-color: var(--mainBg-color);
    }
}
</style>