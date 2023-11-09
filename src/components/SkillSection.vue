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
                <div v-for="(skill, key) in skillText" key="key">
                    <span>{{ key + 1 }}.</span>
                    <h3>{{ skill.title }}</h3>
                    <p>
                        {{ skill.desc }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>
<style lang="scss">
.skill__inner {
    padding: 16px;
    display: flex;
    justify-content: space-between;
    color: var(--subBg300);
    height: 100%;
}

.skill__title {
    position: sticky;
    top: 70px;
    left: 0;
    width: 48%;
    height: 5vw;
    font-size: 4vw;
    font-weight: 900;
    line-height: 1.6;
    text-transform: uppercase;
    color: var(--subBg300);
    border-bottom: 0.5vw solid var(--subBg400);
}

.skill__title em {
    font-size: 1.25rem;
    font-weight: 400;
}

.skill__desc {
    width: 50%;
}

.skill__desc span {
    font-size: 5vw;
    line-height: 1;
    font-weight: 900;
    display: block;
    margin-bottom: 2vw;
    color: var(--subBg300);
}

.skill__desc h3 {
    font-size: 1.3rem;
    text-decoration: underline;
    text-underline-position: under;
    margin-bottom: 1vw;
    color: var(--subBg400);
}

.skill__desc p {
    margin-bottom: 30vh;
    font-size: 1.1rem;
    word-break: keep-all;
    color: var(--subBg300);
}

.skill__desc>div {
    margin-bottom: 30vh;
}

@media (max-width: 800px) {
    .skill__inner {
        flex-direction: column;
    }

    .skill__title {
        width: 100%;
        margin-bottom: 10vw;
        height: auto;
        background-color: var(--);
    }

    .skill__desc {
        width: 100%;
    }

    .skill__desc span {
        font-size: 20vw;
    }
}
</style>