<script setup>
import { headerNav } from "@/constants/index"
</script>

<template>
    <header id="header" role="banner">
        <div class="header__inner">
            <div class="header__logo">
                <a href="#">portfolio <em>coconut</em></a>
            </div>
            <nav class="header__nav" role="navigation" aria-label="메인 메뉴" :class="{ show: isNavVisible }">
                <ul>
                    <li v-for="(nav, key) in headerNav" :key="key">
                        <a :href="nav.url" @click="scrollLink($event)">{{ nav.title }}</a>
                    </li>
                </ul>
            </nav>
            <div class="header__nav__mobile" id="headerToggle" aria-controls="primary-menu"
                :aria-expanded="isNavVisible.toString()" role="button" @click="toggleMobileMenu">
                <span></span>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            isNavVisible: false,
        };
    },
    methods: {
        toggleMobileMenu() {
            // alart("확인");
            this.isNavVisible = !this.isNavVisible;
        },
        scrollLink(event) {
            event.preventDefault();

            const targetId = event.target.getAttribute("href");
            const targetElement = document.querySelector(targetId);

            if (targetElement) {
                targetElement.scrollIntoView({ behavior: "smooth" });
            }
        },
    },

    // react에서는
    // const [show, setShow] = useState(false);

    // const toggleMenu = () => {
    //     setShow((prevShow) => !prevShow);
    // }
};
</script>

<style lang="scss">
#header {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    z-index: 10000;
}

.header__inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: var(--subBg400);
    padding: 1rem;
}

.header__logo {
    display: flex;
    font-size: 20px;
    text-align: center;
    text-transform: uppercase;
    line-height: 1;
    color: var(--mainBg-color);
}

.header__logo a:hover {
    color: var(--mainBg-color);
}

.header__logo em {
    font-size: 10px;
    display: block;
}

.header__nav li {
    display: inline;
}

.header__nav li a {
    text-transform: uppercase;
    font-size: 1rem;
    padding: 1rem;
    position: relative;
    color: var(--mainBg-color);
}

.header__nav li a::before {
    content: '';
    width: calc(100% - 24px);
    height: 1px;
    background-color: var(--mainBg-color);
    position: absolute;
    left: 12px;
    bottom: 13px;
    transform: scaleX(0);
    transition: all 0.3s;
}

.header__nav li a:hover::before {
    transform: scaleX(1);
}

.header__nav__mobile {
    width: 40px;
    height: 40px;
    display: none;
}

.header__nav__mobile span {
    display: block;
    width: 40px;
    height: 2px;
    background-color: var(--mainBg-color);
    margin-top: 19px;
    position: relative;
}

.header__nav__mobile span::before {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--mainBg-color);
    position: absolute;
    right: 0;
    top: 6px;
    transition: width 0.3s;
}

.header__nav__mobile span::after {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--mainBg-color);
    position: absolute;
    left: 0;
    bottom: 6px;
    transition: width 0.3s;
}

@media (max-width: 800px) {
    .header__nav {
        display: none;
    }

    .header__nav.show {
        display: block;
    }

    .header__nav.show ul {
        display: block;
        position: absolute;
        right: 0;
        top: 68px;
        background-color: var(--subBg400);
        z-index: 10000;
        width: 159px;
        padding: 20px 0;
    }

    .header__nav.show li {
        display: block;
        text-align: right;
    }

    .header__nav.show li a {
        display: inline-block;
        padding: 1rem;
    }

    .header__nav.show+.header__nav__mobile span::before {
        width: 20px;
    }

    .header__nav.show+.header__nav__mobile span::after {
        width: 20px;
    }

    .header__nav__mobile {
        display: block;
    }
}
</style>