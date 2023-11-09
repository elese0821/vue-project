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
                <article :class="`port__item p${key + 1}`" v-for="(art, key) in portText" :key="key">
                    <span class="num">{{ art.num }}.</span>
                    <a :href="art.code" target="_blank" class="img">
                        <img :src="art.img" :alt="art.name" />
                    </a>
                    <h3 class="title">{{ art.title }}</h3>
                    <p class="desc">
                        {{ art.desc }}
                    </p>
                    <a :href="art.view" target="_blank" class="site">{{ art.name }}</a>
                </article>
            </div>
        </div>
    </section>
</template>
<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
    mounted: function () {
        this.scrollAnimation();
    },
    methods: {
        scrollAnimation() {
            const horSection = gsap.utils.toArray(".port__item");

            gsap.to(horSection, {
                xPercent: -120 * (horSection.length - 1),
                ease: "none",
                scrollTrigger: {
                    trigger: "#port",
                    start: "top top",
                    end: "+=3000",
                    pin: true,
                    scrub: 1,
                    markers: false,
                    invalidateOnRefresh: true,
                    anticipatePin: 1,
                }
            });
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

.port__title {
    position: sticky;
    top: 70px;
    left: 0;
    width: 70%;
    height: 5vw;
    font-size: 4vw;
    font-weight: 900;
    line-height: 1.6;
    font-family: var(--mainKor-font);
    text-transform: uppercase;
    color: var(--white200);
    border-bottom: 0.4vw solid var(--white200);
    margin-bottom: 100px;
}

.port__title em {
    font-size: 1.25rem;
    font-weight: 400;
    line-height: 2;
}

.port__wrap {
    display: flex;
    flex-wrap: wrap;
    width: 7000px;
}

.port__item {
    width: 500px;
    height: 70vh;
    background-color: var(--white200);
    margin-right: 20px;
    padding: 2.5rem;
}

.port__item .num {
    font-size: 2rem;
    font-family: var(--mainNum-font);
}

.port__item .img {
    display: block;
    margin-top: -20px;
    transition: margin-top 0.3s;
}

.port__item:hover .img {
    margin-top: 0;
}

.port__item .img img {
    border-radius: 5px;
    filter: saturate(0%);
    transition: all 0.3s;
}

.port__item .img:hover img {
    filter: saturate(100%)
}

.port__item .title {
    font-size: 1.5rem;
    text-align: center;
    padding: 0.8rem 0;
    font-weight: 700;
    color: var(--black100);
    border-bottom: 2px solid var(--black100);
    margin-bottom: 1rem;
    font-family: var(--mainKor-font);
}

.port__item .desc {
    font-size: 1rem;
    font-family: var(--mainKor-font);
}

.port__item .site {
    border: 1px solid var(--black100);
    display: block;
    text-align: center;
    padding: 0.625rem 1.5rem;
    margin-top: 1.5rem;
}

.port__item.p1 {
    background-color: var(--subBg100);
}

.port__item.p2 {
    background-color: var(--subBg500);
}

.port__item.p3 {
    background-color: var(--subBg200);
}

.port__item.p4 {
    background-color: var(--subBg400);
}

.port__item.p5 {
    background-color: var(--subBg500);
}

.port__item.p6 {
    background-color: var(--subBg100);
}

.port__item.p7 {
    background-color: var(--subBg500);
}

.port__item.p8 {
    background-color: var(--subBg300);
}

.port__item.p9 {
    background-color: var(--subBg200);
}

.port__item.p10 {
    background-color: var(--subBg500);
}
</style>