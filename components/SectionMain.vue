<template>
  <section class="section-main">
    <div class="wrap">
      <div class="slog-block">
        <div class="content">

          <Title>
            <div class="img"><img src="../static/img/icons/cool.svg" alt="icon"></div>
            <h1>Володарі Трафіку</h1>
            <div class="img revers"><img src="../static/img/icons/cool.svg" alt="icon"></div>
          </Title>
          <div class="desc"><p>SC Partners – нова партнерська мережа з величезним досвідом та експертизою. Кожен наш партнер отримує очікувану вигоду на абсолютно прозорих умовах та бездоганний супровід. Ми будемо поряд з вами: на відстані одного повідомлення в месенджері або дзвінка, адже ми працюємо поряд з вами.</p></div>
          <Rating/>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {}
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';
::v-deep {
  .title {
    align-items: flex-start;
    @media (max-width: $mob) {
      margin-bottom: 20px;
    }
    h1 {
      margin: 0 10px;
    }
  }
}

.img {
  position: relative;
  width: 38px;
  height: 45px;
  @media (max-width: $mob) {
    width: 20px;
    height: 25px;
  }
  &.revers {
    img {
      transform: scaleX(-1);
    }
  }
  img {
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    margin: auto;
    max-width: 100%;
    max-height: 100%;
    width: 100%;
  }
}

.slog-block {
  border-radius: 25px;
  background-color: #23262F80;
  padding: 40px 44px;
  max-width: 900px;
  margin: 0 auto;
  text-align: center;
  position: relative;
  @media (max-width: $mob) {
    padding: 25px;
  }
  .content {
    position: relative;
    z-index: 2;
  }
  .desc {
    margin-bottom: 25px;
  }
  &:before,
  &:after {
     content: '';
     display: block;
     position: absolute;
     width: 100%;
     height: 100%;
     left: 0;
     top: 50%;
     transform: translateY(-50%);
     background-size: cover;
     background-repeat: no-repeat;
     background-position: center;
     z-index: 1;
  }
  &:before {
     background-image: url("static/img/decor/graph-1.svg");
     max-height: 180px;
  }
  &:after {
    background-image: url("static/img/decor/graph-2.svg");
    max-height: 130px;
  }
}

.section-main {
  padding: 100px 0 0;
  @media (max-width: $table) {
    padding: 70px 0 0;
  }
  @media (max-width: $mob) {
    order: 2;
    padding: 50px 0 70px;
  }
}
</style>
