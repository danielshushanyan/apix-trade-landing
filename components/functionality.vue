<template>
  <section id="functionality" class="functionality">
    <div class="wrapper">
      <h2 v-in-viewport.once class="fade-in">
        {{ $t('index.functionality.title') }}
      </h2>
      <p
        v-in-viewport.once
        class="fade-in small"
        v-html="$t('index.functionality.text')"
      ></p>
      <div class="functionality__wrap">
        <div class="functionality__col">
          <video ref="video" muted loop autoplay playsinline>
            <source
              src="~assets/video/functionaly/video.mp4"
              type="video/mp4"
            />
            <source
              src="~assets/video/functionaly/video.webm"
              type="video/webm"
            />
            <source
              :src="require('~/assets/video/functionaly/video.mov').default"
              type="video/quicktime"
            />
          </video>
          <video ref="video" muted loop autoplay playsinline>
            <source
              src="~assets/video/functionaly/video-mobile.mp4"
              type="video/mp4"
            />
            <source
              src="~assets/video/functionaly/video-mobile.webm"
              type="video/webm"
            />
            <source
              :src="
                require('~/assets/video/functionaly/video-mobile.mov').default
              "
              type="video/quicktime"
            />
          </video>
        </div>
        <div class="functionality__col">
          <h5 v-in-viewport.once class="functionality__sub-title fade-in">
            {{ $t('index.functionality.sub_title') }}
          </h5>
          <ul class="functionality__list">
            <li
              v-for="(item, i) in $t('index.functionality.list')"
              :key="i"
              v-in-viewport.once
              class="functionality__list-item fade-in"
            >
              <p class="medium" v-html="item"></p>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: '',
  components: {},
  props: {},
  data() {
    return {}
  },
}
</script>

<style lang="scss" scoped>
.functionality {
  padding: 0 0 40px;
  text-align: center;

  h2 {
    background-image: linear-gradient(
      90deg,
      #9dfff9 0%,
      #75c8fd 25%,
      #72c1fd 50%,
      #6ca2fc 75%,
      #8868fb 100%
    );
    color: transparent;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    margin: 0 auto 10px;
  }

  .wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .wrapper > p {
    margin: 0 auto 85px auto;
    max-width: 840px;
    white-space: pre-line;
    background-image: linear-gradient(to right, #6dcaff, #c663ff),
      linear-gradient(to left, #bfbccd, #bfbccd);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    color: transparent;
    font-weight: 600;
    line-height: 1;
  }

  &__wrap {
    display: flex;
  }

  &__col {
    &:first-child {
      margin: 0 0 0 0;
    }

    &:last-child {
      text-align: left;
      padding: 20px 0 0;
      flex: 1 0 450px;
      max-width: 450px;
      width: 100%;
    }
  }

  video {
    margin-top: -100px;
    position: relative;
    z-index: 1;
    max-width: 100%;
    mix-blend-mode: screen;

    &:nth-child(2) {
      display: none;
    }

    @include bp(640px) {
      display: none;
      &:nth-child(2) {
        display: block;
      }
    }
  }

  &__sub-title {
    margin: 0 0 30px;

    @include bp(1200px) {
      text-align: center;
    }
  }

  &__list {
    text-align: left;

    &-item {
      display: flex;
      padding: 0 0 0 30px;
      color: #6e7594;

      &:first-child,
      &:nth-child(2) {
        margin: 0 0 50px;
      }

      p {
        font-weight: 600;

        ::v-deep b {
          font-weight: 600;
          color: #99a7b8;
        }
      }
    }
  }

  @include bp(1200px) {
    &__wrap {
      flex-direction: column;
      margin: 0 0 80px;
    }

    &__col {
      &:first-child {
        margin: -10% 0;
      }

      &:last-child {
        padding: 0;
        flex: 1;
        margin: 0 auto;
      }
    }

    &__img {
      left: -2.5%;
    }
  }

  @include bp(768px) {
    h2 {
      display: block;
      width: 270px;
    }
    &__list {
      &-item {
        p {
          &:first-child {
            text-align: center;
            min-width: 21px;
          }
        }
      }
    }
  }
}
</style>
