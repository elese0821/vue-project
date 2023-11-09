<script setup>
import { headerNav } from "@/constants/index"
</script>

<template>
    <header id="header" role="banner">
        <div class="header__inner">
            <div class="header__logo">
                <a href="#">portfolio <em>vite</em></a>
            </div>
            <nav class="header__nav" role="navigation" aria-label="메인 메뉴" :class="{ show: isNavVisible }">
                <ul>
                    <li v-for="(nav, key) in headerNav" :key="key">
                        <a :href="nav.url" @click="navlink($event)">{{ nav.title }}</a>
                    </li>
                </ul>
            </nav>
            <div class="header__nav__mobile" id="headerToggle" aria-controls="primary-menu" aria-expanded="false"
                role="button" :aria-expanded="isNavVisible.toString()" @click="toggleMobileMenu">
                <span></span>
            </div>
        </div>
    </header>
    <!-- //header -->
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
};
</script>
<style lang="scss">
#header {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    z-index: 10000;
    box-shadow: 0 2px 2px rgba(0, 0, 0, 0.1);
    font-family: var(--mainEng--font);
}

.header__inner {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #2b3230a6;
    padding: 1rem;
    backdrop-filter: blur(2px);
}

.header__logo {
    color: var(--subBg400);
    font-weight: 700;
    font-size: 1.2rem;
    width: 200px;
}

.header__logo a {
    transition: color 0.3s;
    color: var(--subBg300);
    display: flex;
    justify-content: space-between;
    font-size: 1.2rem;
    align-items: center;
    text-transform: uppercase;
}

.header__logo:hover em {
    color: var(--subBg500);
}

.header__logo em {
    display: block;
    font-size: 1.2rem;
    color: var(--subBg400);
    transition: color 0.3s;
    text-transform: uppercase;
    font-size: 1rem;
}

.header__nav {
    width: calc(100% - 200px);
    display: flex;
    flex-direction: row-reverse;
    font-weight: 600;
}

.header__nav ul {
    display: flex;
}

.header__nav li {
    text-align: center;
    color: var(--mainBg-color);
    font-weight: 500;
    box-sizing: border-box;
    font-size: 1.2rem;

}

.header__nav li a {
    display: block;
    padding: 0 25px;
    border-radius: 20px;
    transition: color 0.2s, background-color 0.3s;
    margin: 5px;
}

.header__nav li a {
    position: relative;
    display: inline-block;
}

.header__nav li a::before {
    content: '';
    width: calc(100% - 30px);
    height: 1px;
    background-color: var(--mainBg-color);
    left: 15px;
    bottom: 0;
    position: absolute;
    transform: scaleX(0);
    transition: all 0.3s;
}

.header__nav li a:hover::before {
    transform: scaleX(1);
}

.header__nav__mobile {
    width: 40px;
    height: 40px;
    cursor: pointer;
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
    top: 6px;
    right: 0;
    transition: width 0.3s;
}

.header__nav__mobile span::after {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--mainBg-color);
    position: absolute;
    bottom: 6px;
    left: 0;
    transition: width 0.3s;
}

@media (max-width:800px) {
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
        z-index: 10000;
        min-width: 159px;
        padding: 20px 0;
        border-radius: 0 0 15px 15px;
        box-shadow: -1px 2px 2px rgba(0, 0, 0, .1);
        backdrop-filter: blur(2px);
        background-color: #2b3230a6;
    }

    .header__nav.show ul li {
        display: block;
    }

    .header__nav.show+.header__nav__mobile span::before {
        width: 20px;
    }

    .header__nav.show+.header__nav__mobile span::after {
        width: 20px;
    }

    .header__nav.show li a {
        display: inline-block;
        padding: 10px;
    }

    .header__nav__mobile {
        display: block;
    }
}
</style>