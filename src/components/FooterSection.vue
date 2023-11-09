<script setup>
import { footerText } from "@/constants/index"
</script>

<template>
    <footer id="footer" role="contentinfo">
        <div class="footer__inner">
            <h2 class="footer__text">
                <div>Coconutpalmtreeisland</div>
                <div>@coconut</div>
            </h2>
            <div class="footer__info">
                <div class="left">
                    <div class="title">
                        <a href="#">sign up</a>
                    </div>
                    <p class="desc">회원가입을 하시면 댓글과 게시판 기능을 이용할 수 있습니다.</p>
                </div>
                <div class="right">
                    <h3>social</h3>
                    <ul v-for="(footer, key) in footerText" :key="key">
                        <li>
                            <a href="footer.link">{{ footer.title }}</a>
                            <em>{{ footer.desc }}</em>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="footer__right">
                &copy; 2023 Coconutpalmtreeisland 이 사이트는 비트를 이용하여 제작하였습니다.
            </div>
        </div>
    </footer>
    <!-- //footer -->
</template>

<style lang="scss">
#footer {
    width: 100%;
}

.footer__inner {
    padding: 16px;
    background-color: var(--subBg400);
    color: var(--mainBg-color);
}

.footer__text {
    display: flex;
    justify-content: space-between;
    font-size: 25px;
    border-bottom: 1px solid var(--mainBg-color);
    margin-bottom: 10px;
}

.footer__info .title a,
.footer__info .right h3 {
    font-size: 20px;
    font-weight: bold;
}

.footer__info {
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
}

.footer__info .left,
.footer__info .right {
    width: 50%;
}

.footer__info .right a {
    font-weight: bold;
    margin-right: 5px;
}

.footer__right {
    display: flex;
    justify-content: flex-end;
    font-size: 14px;
    color: var(--subBg200);
    padding-top: 10px;
    border-top: 1px solid var(--mainBg-color);

}
</style>