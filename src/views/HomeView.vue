<script>
import { gsap } from 'gsap';
import ScrollTrigger from 'gsap/dist/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

export default {
  methods: {
    scroller() {
      const { top1, top2, top3 } = this.$refs;

      const tl1 = gsap.timeline();
      const tl2 = gsap.timeline();
      const tl3 = gsap.timeline();

      tl1.to(top1, {
        x: 10,
      });
      tl2.from(top2, {
        opacity: 0,
      });
      tl3.to(top3, {
        x: 50,
      });

      ScrollTrigger.create({
        animation: tl1,
        trigger: top1,
        start: 'top top',
        scrub: 1,
        pin: true,
        markers: true,
      });
      ScrollTrigger.create({
        animation: tl2,
        trigger: top2,
        start: 'top top',
        scrub: 1,
        pin: true,
        markers: true,
      });
      ScrollTrigger.create({
        animation: tl3,
        trigger: top3,
        start: 'top top',
        scrub: 1,
        pin: true,
        markers: true,
      });

      // const tl = gsap.timeline();

      // tl.to(top1, {
      //   yPercent: -100,
      // })
      //   .to(top2, {
      //     xPercent: -100,
      //   })
      //   .to(top3, {
      //     x: 50,
      //   });

      // ScrollTrigger.create({
      //   animation: tl,
      //   trigger: box,
      //   start: 'top top',
      //   scrub: 1,
      //   pin: true,
      //   markers: true,
      // });
    },
  },
  mounted() {
    this.scroller();
  },
};
</script>

<template>
  <section ref="box">
    <div class="top1-img" ref="top1"></div>
    <div class="top2-img" ref="top2"></div>
    <div class="top3-img" ref="top3"></div>
  </section>
</template>

<style scoped>
.top1-img {
  background-image: url('@/assets/top1-RS660.png');
  width: 100vw;
  height: 100vh;
  background-size: cover;
  background-position: center;
}
.top2-img {
  background-image: url('@/assets/top2-Ninja400.png');
  width: 100vw;
  height: 100vh;
  background-size: cover;
  background-position: 50% 75%;
}
.top3-img {
  background-image: url('@/assets/top3-R6.png');
  width: 100vw;
  height: 100vh;
  background-size: cover;
  background-position: 50% 85%;
}
</style>
