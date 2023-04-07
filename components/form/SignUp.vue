<template>
  <div class="block">
    <div class="vantage-block">
      <div class="graph-block"></div>
      <template>
        <div class="carousel-wrapper">
          <div v-swiper:mySwiper="options">
            <div class="swiper-wrapper">
              <div v-for="i in 3" :key="i" class="swiper-slide">
                <span class="title-block">Зможеш обрати свій варіант</span>
                <CommonAdvan/>
              </div>
            </div>
            <div class="action-slider">
              <div class="swiper-button-prev">
                <svg class="icon">
                  <use xlink:href="#arrow-right" href="img/sprite.svg#arrow-right"></use>
                </svg>
              </div>
              <div class="swiper-pagination swiper-pagination-bullets"></div>
              <div class="swiper-button-next">
                <svg class="icon">
                  <use xlink:href="#arrow-right" href="img/sprite.svg#arrow-right"></use>
                </svg>
              </div>
            </div>
          </div>
        </div>
      </template>
    </div>
    <div class="form-block">
      <slot name="title-modal"></slot>
      <Form>
        <Input type="text" placeholder="Ваше імʼя"/>
        <Input type="text" placeholder="Ваш email"/>
        <Input type="password"
               placeholder="Ваш пароль"
               inputType="password"/>
        <Input type="password"
               placeholder="Повторіть пароль"
               inputType="password"/>
        <SocialConnect/>
        <Button class="large">Реєстрація</Button>
      </Form>
    </div>
  </div>
</template>

<script>
import Form from './Form';
import Input from './Input';
import SocialConnect from './SocialConnect';
import CommonAdvan from '../commonAdvan/CommonAdvan';


export default {
  name: "SignUp",
  components: {Form,
            Input,
            SocialConnect,
            CommonAdvan,
  },
  data() {
    return {
      options: {
        slidesPerView: 1,
        loop: true,
        pagination: {
          el: '.swiper-pagination'
        },
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev",
        },
      }
    }
  }
}
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';

.block-choice {
  margin-top: 25px;
  .title-block {
    font-family: $rb;
    font-size: 12px;
    font-weight: 700;
    line-height: 12px;
    letter-spacing: 0em;
    text-align: center;
    display: block;
    margin-bottom: 10px;
  }
  .action-btn {
    display: flex;
    align-items: center;
  }
  .field {
    margin-left: 10px;
  }
}

.graph-block {
  position: absolute;
  left: 0;
  top: -1px;
  height: 165px;
  width: 100%;
  filter: brightness(6);
  opacity: 0.4;
  &:before,
  &:after {
    content: '';
    display: block;
    position: absolute;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    opacity: 0.5;
    z-index: 1;
  }
  &:before {
    background-image: url("static/img/decor/modal-graph.svg");
    max-height: 182px;
  }
  &:after {
    background-image: url("static/img/decor/modal-graph2.svg");
    max-height: 130px;
    left: 0px;
    top: 7px;
  }
}

.modal-signUp {
  @media (min-width: 1025px) {
    .title-modal {
      flex-direction: column;

      ::v-deep {
        .icon-view {
          margin: 0 0 10px;
        }
      }
    }
  }
}

.form-block,
.vantage-block{
  width: 50%;
  @media (max-width: $table) {
    width: 100%;
  }
}

.form-block {
  padding: 60px 45px 45px;
  @media (max-width: $table) {
    padding: 25px 30px;
  }
}

.block {
  display: flex;
}

.vantage-block {
  background: $green;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 65px 53px 105px;
  overflow: hidden;
  @media (max-width: $table) {
   display: none;
  }
  &:before {
      content: '';
      width: 100%;
      min-height: 161px;
      background-image: url("static/img/decor/lines.svg");
      background-position: bottom;
      display: block;
      background-repeat: no-repeat;
      background-size: cover;
      position: absolute;
      left: 0;
      bottom: 0;
    }

  ::v-deep {
      * {
        color: #fff;
      }
    }

  .title-block {
    font-family: $gl;
    font-weight: 400;
    font-size: 25px;
    line-height: 40px;
    text-align: left;
    max-width: 235px;
  }
}

.swiper-button-prev, .swiper-button-next {
  position: static;
  background-image: none;
  margin: 0;
  width: 25px;
  height: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  .icon {
    width: 16px;
    height: 16px;
  }
}

.swiper-button-prev {
  .icon {
    transform: rotate(180deg);
  }
}

.action-slider {
  display: flex;
  align-items: center;
  justify-content: center;
}

.swiper-pagination {
  position: static;
  display: flex;
  align-items: center;
  justify-content: center;
  ::v-deep {
    .swiper-pagination-bullet {
      background: #fff;
      opacity: 1;
      margin: 0 5px;
      &.swiper-pagination-bullet-active {
        background: $primary;
      }
    }
  }
}

.carousel-wrapper {
  width: 100%;
  height: 100%;
  .swiper-slide {
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
  }
  ::v-deep.swiper-pagination-bullet-active {
    background-color: black;
  }
}

.swiper-container {
  height: 100%;
  padding-bottom: 25px;
}
</style>
