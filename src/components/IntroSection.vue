<template>
    <section id="intro">
        <div class="intro_inner">
            <h1 class="intro__title">
                welcome to my island
            </h1>
            <div class="intro__lines" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
            <div class="intro__text">
                <div class="img"></div>
                <div class="text">
                    <div>There is</div>
                    <div>a light</div>
                    <div>that never</div>
                    <div>goes out</div>
                </div>
            </div>
            <div class="intro__lines bottom" aria-hidden="true">
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
    <!-- //intro -->
</template>
<style lang="scss">
#intro {
    height: 100vh;
}

.intro_inner {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    flex-direction: column;
    padding: 1vw;
}

.intro__title {
    font-size: 7.08vw;
    text-transform: uppercase;
    font-weight: 600;
    font-family: var(--mainTitle-font);
    color: var(--mainfont-color);
    line-height: 0.8;
    letter-spacing: 0.2vw;
}

.intro__lines {
    display: block;
    width: 100%;
}

.intro__lines .line {
    display: block;
    width: 100%;
    height: 1px;
    background-color: var(--subBg300);
    margin-bottom: 0.5vw;
}

.intro__lines .line:nth-child(1) {
    height: 1px;
}

.intro__lines .line:nth-child(2) {
    height: 2px;
}

.intro__lines .line:nth-child(3) {
    height: 3px;
}

.intro__lines .line:nth-child(4) {
    height: 4px;
}

.intro__lines .line:nth-child(5) {
    height: 5px;
}

.intro__lines .line:nth-child(6) {
    height: 6px;
}

.intro__lines .line:nth-child(7) {
    height: 7px;
}

.intro__lines.bottom {
    display: none;
}

.intro__lines.bottom .line:nth-child(1) {
    height: 7px;
}

.intro__lines.bottom .line:nth-child(2) {
    height: 6px;
}

.intro__lines.bottom .line:nth-child(3) {
    height: 5px;
}

.intro__lines.bottom .line:nth-child(4) {
    height: 4px;
}

.intro__lines.bottom .line:nth-child(5) {
    height: 3px;
}

.intro__lines.bottom .line:nth-child(6) {
    height: 2px;
}

.intro__lines.bottom .line:nth-child(7) {
    height: 1px;
}

.intro__text {
    position: relative;
    background-color: var(--subBg300);
    width: 100%;
    /* height: 40vh; */
    padding: 10vw 0;
    display: flex;
    align-items: center;
    text-align: center;
    justify-content: center;
}

.intro__text .text {
    font-family: var(--mainTitle-font);
    font-size: 3vw;
    font-weight: 800;
    line-height: 1.1;
    letter-spacing: 0.1vw;
    color: var(--mainBg-color);
    text-transform: uppercase;
    z-index: 1;
    position: relative;
}

.intro__text:hover .text {
    opacity: 0;
}

.intro__text .img {
    position: absolute;
    width: 15vw;
    height: 15vw;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background-image: url(https://images.unsplash.com/photo-1527707471127-c3ad5ea438d2?auto=format&fit=crop&q=80&w=1587&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D);
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    filter: grayscale(100%);
    transition: all 0.3s;
    border: 0;
    border-radius: 50%;
}

.intro__text:hover .img {
    filter: grayscale(0);
}

@media (max-width: 800px) {
    .intro__inner {
        justify-content: center;
    }

    .intro__lines.bottom {
        display: block;
    }

    .intro__title {
        text-align: center;
        display: none;
    }

    .intro__text .text {
        font-size: 30px;
    }

    .intro__text .text div:nth-child(2) {
        filter: drop-shadow(3px 2px 1px var(--subBg300));
    }

    .intro__text:hover .text {
        opacity: 1;
    }

    .intro__text .img {
        width: 300px;
        height: 300px;
        filter: grayscale(0);
    }
}
</style>