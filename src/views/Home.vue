<template>
  <div class="page-wrapper" :class="{'is-open': burgerOpen}">
    <section class="intro-section parent-container">
      <div class="container">
        <div class="header">
          <img class="logo" src="@/assets/img/logo.svg" alt="Loopstudio" />

          <nav class="nav-links">
            <a href="#">About</a>
            <a href="#">Careers</a>
            <a href="#">Events</a>
            <a href="#">Products</a>
            <a href="#">Support</a>
          </nav>

          <span class="burger-menu" @click="openBurger">
            <img v-if="!burgerOpen" src="@/assets/img/icon-hamburger.svg" alt="Open Burger" />
            <img v-else src="@/assets/img/icon-close.svg" alt="Close Burger" />
          </span>

          <div class="mobile-menu" :class="{'is-open': burgerOpen}">
            <nav class="mobile-links">
              <a href="#">About</a>
              <a href="#">Careers</a>
              <a href="#">Events</a>
              <a href="#">Products</a>
              <a href="#">Support</a>
            </nav>
          </div>
        </div>

        <div class="content-wrapper">
          <h1>Immersive experiences that deliver</h1>
        </div>
      </div>
    </section>

    <section class="about-section parent-container">
      <div class="container">
        <div class="about-wrapper">
          <div class="img-wrapper"></div>

          <div class="about-content">
            <p class="about-title">
              The leader in interactive VR
            </p>

            <p class="about-text">
              Founded in 2011, Loopstudios has been producing world-class virtual reality projects for some of the best companies around the globe. Our award-winning creations have transformed businesses through digital experiences that bind to their brand.
            </p>
          </div>
        </div>
      </div>
    </section>

    <section class="gallery-section parent-container">
      <div class="container">
        <div class="gallery-header">
          <p class="gallery-title">
            OUR CREATIONS
          </p>

          <a href="#" class="site-btn">See all</a>
        </div>

        <div class="gallery-wrapper">
          <div class="item item-1">
            <p>Deep Earth</p>
          </div>
          <div class="item item-2">
            <p>Night Arcade</p>
          </div>
          <div class="item item-3">
            <p>Soccer Team VR</p>
          </div>
          <div class="item item-4">
            <p>The<br/>grid</p>
          </div>
          <div class="item item-5">
            <p>From up above VR</p>
          </div>
          <div class="item item-6">
            <p>Pocket Borealis</p>
          </div>
          <div class="item item-7">
            <p>The Curiosity</p>
          </div>
          <div class="item item-8">
            <p>Make it fisheye</p>
          </div>
        </div>

        <a href="#" class="site-btn mobile-btn">See all</a>
      </div>
    </section>

    <footer>
      <div class="container">
        <div class="footer-wrapper">
          <div class="left-footer">
            <img src="@/assets/img/logo.svg" alt="Loopstudio" />

            <nav class="nav-links">
              <a href="#">About</a>
              <a href="#">Careers</a>
              <a href="#">Events</a>
              <a href="#">Products</a>
              <a href="#">Support</a>
            </nav>
          </div>

          <div class="right-footer">
            <div class="social-wrapper">
              <a href="#">
                <img src="@/assets/img/icon-facebook.svg" alt="Facebook" />
              </a>
              <a href="#">
                <img src="@/assets/img/icon-twitter.svg" alt="Facebook" />
              </a>
              <a href="#">
                <img src="@/assets/img/icon-pinterest.svg" alt="Facebook" />
              </a>
              <a href="#">
                <img src="@/assets/img/icon-instagram.svg" alt="Facebook" />
              </a>
            </div>

            <p>© 2021 Loopstudios. All rights reserved</p>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  data() {
    return {
      burgerOpen: false
    }
  },
  head() {
    return {
      title: {
        inner: 'Home'
      },
      meta: [
        {
          name: 'description',
          content: `${this.appTitle} home page`,
          id: 'desc'
        }
      ]
    }
  },
  methods: {
    openBurger() {
      this.burgerOpen = !this.burgerOpen
    }
  },
  computed: mapState('app', ['appTitle'])
}
</script>

<style lang="scss" scoped>
@import '@/theme/variables.scss';

.page-wrapper {
  display: flex;
  flex-direction: column;

  &.is-open {
    max-height: 100vh;
    overflow: hidden;
  }
}

.intro-section {
  position: relative;
  background: url('../assets/img/desktop/image-hero.jpg') top center/cover no-repeat;
  min-height: 650px;

  @media (max-width: 767px) {
    background: url('../assets/img/mobile/image-hero.jpg') center/cover no-repeat;
  }

  .header {
    display: flex;
    align-items: center;
    padding-top: 64px;

    @media (max-width: 767px) {
      padding-top: 40px;
    }

    .nav-links {
      display: flex;
      align-items: center;
      margin-left: auto;

      @media (max-width: 767px) {
        display: none;
      }

      a {
        position: relative;
        font-weight: normal;
        font-family: $font1;
        font-size: 15px;
        line-height: 25px;
        color: $white;

        &:not(:last-child) {
          margin-right: 32px;
        }

        &:hover {
          &:after {
            height: 2px;
          }
        }

        &:after {
          content: '';
          position: absolute;
          bottom: -8px;
          left: 0;
          right: 0;
          margin: auto;
          height: 0;
          width: calc(100% - 30px);
          background: $white;
          transition: height 0.15s ease-in-out;
        }
      }
    }

    .logo {
      position: relative;
      z-index: 11;
    }

    .burger-menu {
      position: relative;
      margin-left: auto;
      cursor: pointer;
      z-index: 11;

      @media (min-width: 768px) {
        display: none;
      }
    }

    .mobile-menu {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: $black;
      opacity: 0;
      pointer-events: none;
      z-index: 10;
      transition: opacity .3s ease-in-out;

      @media (min-width: 768px) {
        pointer-events: none;
        opacity: 0;
        z-index: -1;
      }

      &.is-open {
        opacity: 1;
        pointer-events: auto;
      }

      .mobile-links {
        padding-left: 24px;
        display: flex;
        align-items: flex-start;
        flex-direction: column;
        justify-content: center;
        height: 100%;

        a {
          font-weight: 300;
          font-size: 24px;
          line-height: 25px;
          color: $white;

          &:not(:last-child) {
            margin-bottom: 24px;
          }
        }
      }
    }
  }

  .content-wrapper {
    position: relative;
    font-family: $font2;
    margin-top: 123px;
    max-width: 650px;
    border: 1px solid $white;
    padding: 40px;

    @media (max-width: 767px) {
      max-width: 327px;
      margin: 163px auto 0;
      padding: 24px;
    }

    h1 {
      font-weight: 300;
      font-size: 72px;
      line-height: 70px;
      color: $white;
      text-transform: uppercase;

      @media (max-width: 767px) {
        font-size: 40px;
        line-height: 38px;
      }
    }
  }
}

.about-section {
  display: flex;
  align-items: flex-end;
  margin-top: 160px;

  @media (max-width: 767px) {
    flex-direction: column;
    margin-top: 96px;
  }

  .about-wrapper {
    display: flex;
    align-items: flex-end;
    position: relative;
    height: 500px;

    @media (max-width: 767px) {
      height: auto;
      flex-direction: column;
    }
  }


  .img-wrapper {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    max-width: 731px;
    height: 500px;
    background: url('../assets/img/desktop/image-interactive.jpg') top left no-repeat;

    @media (max-width: 767px) {
      position: relative;
      width: 100%;
      height: 224px;
      background: url('../assets/img/mobile/image-interactive.jpg') top/cover no-repeat;
    }
  }

  .about-content {
    position: relative;
    z-index: 1;
    max-width: 541px;
    padding: 96px 0 0 96px;
    background: $white;
    margin-left: auto;

    @media (max-width: 767px) {
      max-width: 100%;
      margin-left: 0;
      padding: 48px 0 0;
      text-align: center;
    }

    .about-title {
      font-family: $font2;
      font-weight: 300;
      font-size: 48px;
      line-height: 48px;
      color: $black;
      text-transform: uppercase;
      margin-bottom: 25px;

      @media (max-width: 767px) {
        font-size: 32px;
        line-height: 32px;
        margin-bottom: 16px;
      }
    }

    .about-text {
      font-family: $font2;
      font-weight: normal;
      font-size: 15px;
      line-height: 25px;
      color: $black;
    }
  }
}

.gallery-section {
  margin-top: 184px;

  @media (max-width: 767px) {
    margin-top: 69px;
    text-align: center;
  }

  .gallery-header {
    display: flex;
    align-items: center;
    margin-bottom: 80px;

    @media (max-width: 767px) {
      margin-bottom: 48px;
      justify-content: center;
    }

    .gallery-title {
      font-family: $font2;
      font-weight: 300;
      font-size: 48px;
      line-height: 48px;
      text-transform: uppercase;
      color: $black;

      @media (max-width: 767px) {
        font-size: 32px;
        line-height: 32px;
        text-align: center;
      }
    }

    .site-btn {
      font-family: $font1;
      margin-left: auto;
      padding: 13px 43px;
      font-weight: normal;
      font-size: 14px;
      line-height: 14px;
      letter-spacing: 5px;
      text-transform: uppercase;
      border: 1px solid $black;
      transition: all .3s ease-in-out;
      color: $black;

      @media (max-width: 767px) {
        display: none;
      }

      &:hover {
        color: $white;
        background: $black;
      }
    }
  }

  .gallery-wrapper {
    display: flex;
    align-items: stretch;
    flex-wrap: wrap;
    margin-bottom: -30px;
    padding-bottom: 184px;
    text-align: left;

    @media (max-width: 767px) {
      flex-direction: column;
      padding-bottom: 34px;
    }

    .item {
      position: relative;
      display: flex;
      flex-direction: column;
      width: calc((100% - 90px) / 4);
      margin-bottom: 30px;
      height: 450px;
      padding: 32px 40px;
      cursor: pointer;

      @media (min-width: 1025px) {
        &:not(:nth-child(4)):not(:nth-child(8)) {
          margin-right: 30px;
        }
      }

      @media (min-width: 768px) and (max-width: 1024px) {
        width: calc((100% - 30px) / 2);

        &:not(:nth-child(even)) {
          margin-right: 30px;
        }
      }

      @media (max-width: 767px) {
        width: 100%;
        height: 120px;
        padding: 52px 20px 20px;
      }

      &:after {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: $white;
        pointer-events: none;
        opacity: 0;
        transition: opacity .3s ease-in-out;
        z-index: 1;
      }

      &:hover {
        &:after {
          opacity: 0.75;
        }

        p {
          color: $black;
        }
      }

      &.item-1 {
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/desktop/image-deep-earth.jpg') center/cover no-repeat;

        @media (max-width: 1024px) {
          background-position: top center;
        }

        @media (max-width: 767px) {
          background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%),  url('../assets/img/mobile/image-deep-earth.jpg') center/cover no-repeat;
        }
      }

      &.item-2 {
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/desktop/image-night-arcade.jpg') center/cover no-repeat;

        @media (max-width: 1024px) {
          background-position: top center;
        }

        @media (max-width: 767px) {
          background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/desktop/image-night-arcade.jpg') center/cover no-repeat;
        }
      }

      &.item-3 {
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/desktop/image-soccer-team.jpg') center/cover no-repeat;

        @media (max-width: 1024px) {
          background-position: top center;
        }

        @media (max-width: 767px) {
          background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/mobile/image-soccer-team.jpg') center/cover no-repeat;
        }
      }

      &.item-4 {
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/desktop/image-grid.jpg') center/cover no-repeat;

        @media (max-width: 1024px) {
          background-position: top center;
        }

        @media (max-width: 767px) {
          background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/mobile/image-grid.jpg') center/cover no-repeat;
        }
      }

      &.item-5 {
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/desktop/image-from-above.jpg') center/cover no-repeat;

        @media (max-width: 1024px) {
          background-position: top center;
        }

        @media (max-width: 767px) {
          background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/mobile/image-from-above.jpg') center/cover no-repeat;
        }
      }

      &.item-6 {
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/desktop/image-pocket-borealis.jpg') center/cover no-repeat;

        @media (max-width: 1024px) {
          background-position: top center;
        }

        @media (max-width: 767px) {
          background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/mobile/image-pocket-borealis.jpg') center/cover no-repeat
        }
      }

      &.item-7 {
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/desktop/image-curiosity.jpg') center/cover no-repeat;

        @media (max-width: 1024px) {
          background-position: top center;
        }

        @media (max-width: 767px) {
          background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/mobile/image-curiosity.jpg') center/cover no-repeat;
        }
      }

      &.item-8 {
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/desktop/image-fisheye.jpg') center/cover no-repeat;

        @media (max-width: 1024px) {
          background-position: top center;
        }

        @media (max-width: 767px) {
          background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.601863) 100%), url('../assets/img/mobile/image-fisheye.jpg') center/cover no-repeat;
        }
      }

      p {
        position: relative;
        margin-top: auto;
        font-family: $font2;
        font-weight: 300;
        font-size: 32px;
        line-height: 32px;
        max-width: 170px;
        /* or 100% */

        text-transform: uppercase;
        color: $white;
        z-index: 2;

        @media (max-width: 767px) {
          max-width: 120px;
          font-size: 24px;
          line-height: 24px;
        }
      }
    }
  }

  .mobile-btn {
    display: inline-block;
    font-family: $font1;
    padding: 13px 43px;
    font-weight: normal;
    font-size: 14px;
    line-height: 14px;
    letter-spacing: 5px;
    text-transform: uppercase;
    border: 1px solid $black;
    transition: all .3s ease-in-out;
    color: $black;
    margin: auto auto 96px;
    text-align: center;

    @media (min-width: 768px) {
      display: none;
    }

    &:hover {
      color: $white;
      background: $black;
    }
  }
}

footer {
  background: $black;
  padding: 44px 40px 33px;

  @media (max-width: 767px) {
    padding: 56px 52px;
  }

  .footer-wrapper {
    display: flex;
    align-items: stretch;

    @media (max-width: 767px) {
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
    }

    .left-footer {
      img {
        margin-bottom: 14px;

        @media (max-width: 767px) {
          margin-bottom: 32px;
        }
      }

      .nav-links {
        display: flex;
        align-items: center;

        @media (max-width: 767px) {
          flex-direction: column;
        }

        a {
          position: relative;
          font-weight: normal;
          font-family: $font1;
          font-size: 15px;
          line-height: 25px;
          color: $white;

          &:not(:last-child) {
            margin-right: 32px;

            @media (max-width: 767px) {
              margin-right: 0;
              margin-bottom: 16px;
            }
          }

          &:hover {
            &:after {
              height: 2px;
            }
          }

          &:after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            right: 0;
            margin: auto;
            height: 0;
            width: calc(100% - 30px);
            background: $white;
            transition: height 0.15s ease-in-out;
          }
        }
      }
    }

    .right-footer {
      display: flex;
      flex-direction: column;
      text-align: right;
      margin-left: auto;

      @media (max-width: 767px) {
        margin-left: 0;
        margin-top: 48px;
        text-align: center;
      }

      .social-wrapper {
        margin-bottom: 14px;

        a {
          position: relative;

          &:not(:last-child) {
            margin-right: 16px;
          }

          &:hover {
            &:after {
              height: 2px;
            }
          }

          &:after {
            content: '';
            position: absolute;
            bottom: -16px;
            left: 0;
            right: 0;
            margin: auto;
            height: 0;
            width: 100%;
            background: $white;
            transition: height 0.15s ease-in-out;
          }
        }
      }

      p {
        font-family: $font1;
        margin-top: auto;
        font-weight: normal;
        font-size: 15px;
        line-height: 25px;
        color: $white;
        opacity: 0.5;
      }
    }
  }
}
</style>
