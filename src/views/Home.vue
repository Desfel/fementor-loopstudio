<template>
  <div class="page-wrapper">
    <section class="intro-section">
      <div class="container">
        <div class="header">
          <img src="@/assets/img/logo.svg" alt="Loopstudio" />

          <nav class="nav-links">
            <a href="#">About</a>
            <a href="#">Careers</a>
            <a href="#">Events</a>
            <a href="#">Products</a>
            <a href="#">Support</a>
          </nav>
        </div>

        <div class="content-wrapper">
          <h1>Immersive experiences that deliver</h1>
        </div>
      </div>
    </section>

    <section class="about-section">
      <div class="container">
        <div class="about-wrapper">
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

    <section class="gallery-section">
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
  computed: mapState('app', ['appTitle'])
}
</script>

<style lang="scss" scoped>
@import '@/theme/variables.scss';

.page-wrapper {
  display: flex;
  flex-direction: column;
}

.intro-section {
  position: relative;
  background: url('../assets/img/desktop/image-hero.jpg') top center/cover no-repeat;
  min-height: 650px;

  .header {
    display: flex;
    align-items: center;
    padding-top: 64px;

    .nav-links {
      display: flex;
      align-items: center;
      margin-left: auto;

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
  }

  .content-wrapper {
    font-family: $font2;
    margin-top: 123px;
    max-width: 650px;
    border: 1px solid $white;
    padding: 40px;

    h1 {
      font-weight: 300;
      font-size: 72px;
      line-height: 70px;
      color: $white;
      text-transform: uppercase;
    }
  }
}

.about-section {
  display: flex;
  align-items: flex-end;
  margin-top: 160px;

  .about-wrapper {
    padding-top: 183px;
    background: url('../assets/img/desktop/image-interactive.jpg') top left no-repeat;
  }

  .about-content {
    max-width: 541px;
    padding: 96px 0 0 96px;
    background: $white;
    margin-left: auto;

    .about-title {
      font-family: $font2;
      font-weight: 300;
      font-size: 48px;
      line-height: 48px;
      color: $black;
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

  .gallery-header {
    display: flex;
    align-items: center;
    margin-bottom: 80px;

    .gallery-title {
      font-family: $font2;
      font-weight: 300;
      font-size: 48px;
      line-height: 48px;
      text-transform: uppercase;
      color: $black;
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
          opacity: .75;
        }

        p {
          color: $black;
        }
      }

      &.item-1 {
        background: url('../assets/img/desktop/image-deep-earth.jpg') center/cover no-repeat;
      }

      &.item-2 {
        background: url('../assets/img/desktop/image-night-arcade.jpg') center/cover no-repeat;
      }

      &.item-3 {
        background: url('../assets/img/desktop/image-soccer-team.jpg') center/cover no-repeat;
      }

      &.item-4 {
        background: url('../assets/img/desktop/image-grid.jpg') center/cover no-repeat;
      }

      &.item-5 {
        background: url('../assets/img/desktop/image-from-above.jpg') center/cover no-repeat;
      }

      &.item-6 {
        background: url('../assets/img/desktop/image-pocket-borealis.jpg') center/cover no-repeat;
      }

      &.item-7 {
        background: url('../assets/img/desktop/image-curiosity.jpg') center/cover no-repeat;
      }

      &.item-8 {
        background: url('../assets/img/desktop/image-fisheye.jpg') center/cover no-repeat;
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
      }
    }
  }
}

footer {
  background: $black;
  padding: 44px 40px 33px;

  .footer-wrapper {
    display: flex;
    align-items: stretch;

    .left-footer {
      img {
        margin-bottom: 14px;
      }

      .nav-links {
        display: flex;
        align-items: center;

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
    }

    .right-footer {
      display: flex;
      flex-direction: column;
      text-align: right;
      margin-left: auto;

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
