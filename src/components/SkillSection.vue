<script setup>
import { skillText } from "@/constants/index"
</script>

<template>
    <section id="skill">
        <div class="skill__inner">
            <h2 class="skill__title">
                challenge <em>나의 도전</em>
            </h2>
            <div class="skill__desc">
                <div v-for="(skill, key) in skillText" :key="key">
                    <span>{{ key + 1 }}.</span>
                    <h3>{{ skill.title }}</h3>
                    <p>{{ skill.desc }}</p>
                </div>
            </div>
        </div>
    </section>
    <!-- //skill -->
</template>

<style lang="scss">
.skill__inner {
    padding: 16px;
    display: flex;
    justify-content: space-between;
}

.skill__title {
    position: sticky;
    top: 68px;
    left: 0;
    width: 48%;
    height: 4.9vw;
    font-size: 4vw;
    font-weight: 900;
    line-height: 1.6;
    text-transform: uppercase;
    font-family: var(--mainTitle-font);
    color: var(--mainfont-color);
    border-bottom: 0.3vw solid var(--mainfont-color);
}

.skill__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 400;
    display: inline-block;
}

.skill__desc {
    width: 48%;
}

.skill__desc span {
    font-size: 5vw;
    line-height: 1.5;
    font-weight: 900;
    font-family: var(--mainNum-font);
    color: var(--mainfont-color);
}

.skill__desc h3 {
    font-size: 1.3rem;
    text-decoration: underline;
    text-underline-position: under;
    margin-bottom: 1vw;
    color: var(--mainfont-color);
}

.skill__desc p {
    margin-bottom: 20vh;
    font-size: 1rem;
    font-family: var(--mainKor-font);
    color: var(--mainfont-color);
}

@media (max-width: 800px) {
    .skill__inner {
        flex-direction: column;
    }

    .skill__title {
        width: 100%;
        padding: 10px 0;
        margin-bottom: 10vw;
        height: auto;
        background-color: var(--mainBg-color);
    }

    .skill__desc {
        width: 100%;
    }

    .skill__desc span {
        font-size: 20vw;
    }

    .skill__desc h3 {
        margin-bottom: 2vh;
    }
}
</style>