<script setup>
import { contactText } from "@/constants/index"
</script>
<template>
    <section id="contact">
        <div class="contact__inner">
            <h2 class="contact__title">Contact</h2>

            <div class="contact__lines top" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
            <div class="contact__text">
                <div class="text">
                    <div v-for="(cont, key) in contactText" :key="key">
                        <a :href="cont.link">{{ cont.title }}</a>
                    </div>
                </div>
            </div>
            <div class="contact__lines " aria-hidden="true">
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
</template>
<style lang="scss">
#contact {
    height: 100vh;
}

.contact__inner {
    width: 100%;
    height: 100%;
    padding: 16px;
    display: flex;
    align-items: flex-start;
    justify-content: flex-end;
    flex-direction: column;
}

.contact__title {
    font-size: 10vw;
    text-transform: uppercase;
    line-height: 1;
    font-weight: 800;
    white-space: nowrap;
    text-indent: -0.5vw;
    letter-spacing: -0.3vw;
    font-family: var(--mainPop-font);
    color: var(--mainSub-color)
}

.contact__text {
    width: 100%;
    height: 40vh;
    background-color: var(--black);
    color: var(--mainSub-color);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    position: relative;
    background-color: var(--mainSub-color);
}

.contact__text .text {
    font-size: 3vw;
    line-height: 1;
    font-weight: 900;
    text-transform: uppercase;
    text-decoration: underline;
    text-align: center;
    position: relative;
    z-index: 100;
    transition: all 0.3s;
    cursor: all-scroll;
    font-family: var(--mainPop-font);
    color: var(--mainBg-color)
}

.contact__lines {
    width: 100%;
}

.contact__lines .line {
    display: block;
    width: 100%;
    height: 1px;
    background-color: var(--mainSub-color);
    margin-bottom: 0.5vw;
}

.contact__lines.top .line {
    margin-top: 0.5vw;
    margin-bottom: 0;
    display: none;
}

.contact__lines.top .line:nth-child(1) {
    height: 1px;
}

.contact__lines.top .line:nth-child(2) {
    height: 2px;
}

.contact__lines.top .line:nth-child(3) {
    height: 3px;
}

.contact__lines.top .line:nth-child(4) {
    height: 4px;
}

.contact__lines.top .line:nth-child(5) {
    height: 5px;
}

.contact__lines.top .line:nth-child(6) {
    height: 6px;
}

.contact__lines.top .line:nth-child(7) {
    height: 7px;
}

.contact__lines .line:nth-child(1) {
    height: 7px;
}

.contact__lines .line:nth-child(2) {
    height: 6px;
}

.contact__lines .line:nth-child(3) {
    height: 5px;
}

.contact__lines .line:nth-child(4) {
    height: 4px;
}

.contact__lines .line:nth-child(5) {
    height: 3px;
}

.contact__lines .line:nth-child(6) {
    height: 2px;
}

.contact__lines .line:nth-child(7) {
    height: 1px;
}

@media (max-width: 800px) {
    .contact__title {
        display: none;
    }

    .contact__lines.top .line {
        display: block;
    }

    .contact__text .text {
        font-size: 24px;
        padding: 0 16px;
        word-break: break-all;
    }

    .contact__inner {
        justify-content: center;
    }
}
</style>