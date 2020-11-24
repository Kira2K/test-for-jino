<template>
  <div class="background background_one" ref="background_one">
    <div class="container">
      <div class="flex center">
        <div class="jino">
          <svg
            class="jino-logo jino-logo_white"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 65 15"
          >
            <path
              d="M26.708 7.223L28.2 3.125c.087-.315.05-.587-.095-.797-.148-.21-.392-.338-.65-.338h-2.33c-.354 0-.667.24-.763.582l-.92 3.445h-.687V2.78c0-.437-.354-.792-.79-.792h-1.976c-.44 0-.793.354-.793.792v3.235h-.78l-1.243-3.507c-.116-.31-.412-.52-.746-.52h-2.305c-.268 0-.52.136-.664.363-.15.228-.17.512-.06.828l1.843 4.048-1.86 4.698c-.094.242-.06.516.087.732.148.215.392.344.65.344h2.306c.35 0 .655-.228.758-.562l1.043-3.44h.97v3.21c0 .437.353.79.79.79h1.976c.437 0 .79-.354.79-.79V9h.834l.767 3.387c.087.357.404.613.77.613h2.33c.252 0 .49-.12.64-.32.148-.202.193-.463.12-.705l-1.506-4.752zM40.217 2.417c-.004-.008-.012-.017-.018-.024-.024-.045-.058-.09-.095-.132-.008-.007-.013-.02-.02-.028-.046-.045-.095-.083-.15-.12-.01-.007-.02-.012-.036-.02-.046-.024-.09-.045-.14-.062l-.05-.013c-.062-.016-.128-.03-.194-.03h-1.98c-.06 0-.118.01-.177.022-.018.003-.03.012-.046.016-.04.013-.078.025-.115.045l-.056.026c-.03.02-.064.04-.095.066-.02.012-.033.024-.05.037-.028.032-.062.065-.088.098-.01.008-.017.017-.02.025l-3.27 4.613h-.042V2.78c0-.437-.355-.792-.792-.792h-1.975c-.438 0-.792.354-.792.792v9.427c0 .123.03.238.084.342 0 .008 0 .012.004.02s.013.018.017.02c.028.05.058.096.095.137.008.01.017.017.024.028.042.046.09.082.145.115.012.014.023.018.04.024.04.024.09.046.14.058.018.01.03.014.046.018.068.017.13.03.2.03h1.975c.063 0 .12-.01.178-.02.017-.006.033-.015.05-.02.037-.012.078-.023.115-.044l.05-.028c.032-.017.065-.037.1-.062.012-.013.028-.024.045-.04.032-.03.062-.063.086-.097.01-.013.02-.02.024-.024L36.7 8.12h.045v4.087c0 .438.354.793.79.793h1.98c.438 0 .786-.354.786-.793V2.78c0-.124-.027-.24-.076-.342-.003-.008-.003-.016-.007-.02zM51.225 1.99h-1.98c-.437 0-.786.353-.786.79V6h-2.887V2.78c0-.437-.354-.792-.793-.792h-1.973c-.438 0-.794.354-.794.792v9.427c0 .438.355.79.794.79h1.973c.438 0 .793-.353.793-.79V9h2.886v3.207c0 .438.35.79.786.79h1.98c.437 0 .79-.353.79-.79V2.78c0-.437-.354-.79-.79-.79zM11.084 9.994V2.78c0-.437-.354-.792-.792-.792H3.178c-.437 0-.792.354-.792.792L1.2 9.994H.802c-.433 0-.787.354-.787.79v3.425c0 .436.354.79.787.79h1.583c.438 0 .792-.354.792-.79v-1.147h5.537v1.146c0 .436.35.79.787.79h1.583c.437 0 .792-.354.792-.79v-3.425c0-.437-.356-.79-.793-.79zm-3.1.006l-3.417-.008.77-4.977h2.647V10zM59.28 1.79c-3.374 0-5.73 2.36-5.73 5.735 0 3.375 2.356 5.734 5.73 5.734 3.378 0 5.735-2.357 5.735-5.735 0-3.376-2.357-5.734-5.734-5.734zm0 8.192c-1.56 0-2.456-.896-2.456-2.458 0-1.562.895-2.457 2.457-2.457 1.563 0 2.458.895 2.458 2.457 0 1.564-.894 2.458-2.457 2.458z"
            />
          </svg>
          <p class="jino-domens jino-domens_white">домены</p>
        </div>
        <div class="january">Только до 31 января</div>
      </div>

      <div class="flex center">
        <h1 class="big-text">
          Честная цена <br />
          за домен .RU — 39₽
        </h1>
      </div>

      <div class="flex center">
        <div class="col-8">
          <div class="form">
            <input type="text" class="form__input" v-model="domen" />
            <button class="form__btn">
              <p class="form__btn-text" @click="successMsg = true">Проверить</p>
            </button>
            <div v-if="successMsg" class="form__result">
              <div class="form__msg">
                Домен {{ domen }} — свободен.
                <a href="#" class="form__link"> Зарегистрировать за 39₽</a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="flex center">
        <div class="col-3 create-account create-account_1">
          <button class="create-account__btn">
            <p class="create-account__text">
              Создать аккаунт
            </p>
          </button>
        </div>
      </div>

      <div class="flex center">
        <img
          @click="scroll('background_one')"
          src="@/assets/down2x.png"
          alt=""
          class="arrow"
        />
      </div>
    </div>

    <div class="navigation">
      <div class="navigation__circle navigation__circle_active"></div>
      <a
        href="#test"
        class="navigation__circle"
        @click="scroll('background_one')"
      ></a>
      <div
        class="navigation__circle"
        @click="scroll('background_one', 'background_two')"
      ></div>
    </div>
  </div>
  <div class="background background_two" ref="background_two">
    <div class="container">
      <div class="flex">
        <div class="jino">
          <svg
            class="jino-logo jino-logo_red"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 65 15"
          >
            <path
              d="M26.708 7.223L28.2 3.125c.087-.315.05-.587-.095-.797-.148-.21-.392-.338-.65-.338h-2.33c-.354 0-.667.24-.763.582l-.92 3.445h-.687V2.78c0-.437-.354-.792-.79-.792h-1.976c-.44 0-.793.354-.793.792v3.235h-.78l-1.243-3.507c-.116-.31-.412-.52-.746-.52h-2.305c-.268 0-.52.136-.664.363-.15.228-.17.512-.06.828l1.843 4.048-1.86 4.698c-.094.242-.06.516.087.732.148.215.392.344.65.344h2.306c.35 0 .655-.228.758-.562l1.043-3.44h.97v3.21c0 .437.353.79.79.79h1.976c.437 0 .79-.354.79-.79V9h.834l.767 3.387c.087.357.404.613.77.613h2.33c.252 0 .49-.12.64-.32.148-.202.193-.463.12-.705l-1.506-4.752zM40.217 2.417c-.004-.008-.012-.017-.018-.024-.024-.045-.058-.09-.095-.132-.008-.007-.013-.02-.02-.028-.046-.045-.095-.083-.15-.12-.01-.007-.02-.012-.036-.02-.046-.024-.09-.045-.14-.062l-.05-.013c-.062-.016-.128-.03-.194-.03h-1.98c-.06 0-.118.01-.177.022-.018.003-.03.012-.046.016-.04.013-.078.025-.115.045l-.056.026c-.03.02-.064.04-.095.066-.02.012-.033.024-.05.037-.028.032-.062.065-.088.098-.01.008-.017.017-.02.025l-3.27 4.613h-.042V2.78c0-.437-.355-.792-.792-.792h-1.975c-.438 0-.792.354-.792.792v9.427c0 .123.03.238.084.342 0 .008 0 .012.004.02s.013.018.017.02c.028.05.058.096.095.137.008.01.017.017.024.028.042.046.09.082.145.115.012.014.023.018.04.024.04.024.09.046.14.058.018.01.03.014.046.018.068.017.13.03.2.03h1.975c.063 0 .12-.01.178-.02.017-.006.033-.015.05-.02.037-.012.078-.023.115-.044l.05-.028c.032-.017.065-.037.1-.062.012-.013.028-.024.045-.04.032-.03.062-.063.086-.097.01-.013.02-.02.024-.024L36.7 8.12h.045v4.087c0 .438.354.793.79.793h1.98c.438 0 .786-.354.786-.793V2.78c0-.124-.027-.24-.076-.342-.003-.008-.003-.016-.007-.02zM51.225 1.99h-1.98c-.437 0-.786.353-.786.79V6h-2.887V2.78c0-.437-.354-.792-.793-.792h-1.973c-.438 0-.794.354-.794.792v9.427c0 .438.355.79.794.79h1.973c.438 0 .793-.353.793-.79V9h2.886v3.207c0 .438.35.79.786.79h1.98c.437 0 .79-.353.79-.79V2.78c0-.437-.354-.79-.79-.79zM11.084 9.994V2.78c0-.437-.354-.792-.792-.792H3.178c-.437 0-.792.354-.792.792L1.2 9.994H.802c-.433 0-.787.354-.787.79v3.425c0 .436.354.79.787.79h1.583c.438 0 .792-.354.792-.79v-1.147h5.537v1.146c0 .436.35.79.787.79h1.583c.437 0 .792-.354.792-.79v-3.425c0-.437-.356-.79-.793-.79zm-3.1.006l-3.417-.008.77-4.977h2.647V10zM59.28 1.79c-3.374 0-5.73 2.36-5.73 5.735 0 3.375 2.356 5.734 5.73 5.734 3.378 0 5.735-2.357 5.735-5.735 0-3.376-2.357-5.734-5.734-5.734zm0 8.192c-1.56 0-2.456-.896-2.456-2.458 0-1.562.895-2.457 2.457-2.457 1.563 0 2.458.895 2.458 2.457 0 1.564-.894 2.458-2.457 2.458z"
            />
          </svg>
          <p class="jino-domens jino-domens_black">домены</p>
        </div>
      </div>

      <div class="flex center">
        <h4 class="you-get">Зарегистрировав у нас домен, вы получите</h4>
      </div>

      <div class="flex featuresTop">
        <div
          class="col-3 col-feature"
          v-for="feature in featuresTop"
          :key="feature"
        >
          <div class="feature">
            <img
              :src="require(`@/assets/features/${feature.img}.svg`)"
              alt=""
              class="feature__img"
            />
            <div class="feature__text">{{ feature.text }}</div>
          </div>
        </div>
      </div>

      <div class="flex">
        <div class="col-12">
          <div class="features-description">
            <div class="features-description__arror-wrapper">
              <div class="features-description__arrow"></div>
            </div>

            <p class="features-description__text">
              Для любого вашего домена, зарегистрированного на «Джино», вы
              можете в несколько кликов создать простую страницу-визитку. Это
              удобно, если ваш основной сайт еще не готов, или если домен вам
              нужен только для почты. Вы можете разместить здесь краткую
              информацию о себе или вашем бизнесе, ссылки на аккаунты в соцсетях
              и любые другие сайты. Создание и поддержка базового варианта
              сайта-визитки абсолютно бесплатны.
            </p>
          </div>
        </div>
      </div>

      <div class="flex featuresBottom">
        <div
          class="col-3 col-feature"
          v-for="feature in featuresBottom"
          :key="feature"
        >
          <div class="feature">
            <img
              :src="require(`@/assets/features/${feature.img}.svg`)"
              alt=""
              class="feature__img"
            />
            <div class="feature__text" :class="{ mw: feature.img === 'cloud' }">
              {{ feature.text }}
            </div>
          </div>
        </div>
      </div>

      <div class="flex center">
        <div class="col-3 create-account create-account_2">
          <button class="create-account__btn">
            <p class="create-account__text">
              Создать аккаунт
            </p>
          </button>
        </div>
      </div>
    </div>

    <div class="navigation">
      <div class="navigation__circle " @click="scroll()"></div>
      <div class="navigation__circle navigation__circle_active"></div>
      <div
        @click="scroll('background_one', 'background_two')"
        class="navigation__circle"
      ></div>
    </div>
  </div>
  <div class="background background_three">
    <div class="container">
      <div class="flex">
        <div class="jino">
          <svg
            class="jino-logo jino-logo_white"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 65 15"
          >
            <path
              d="M26.708 7.223L28.2 3.125c.087-.315.05-.587-.095-.797-.148-.21-.392-.338-.65-.338h-2.33c-.354 0-.667.24-.763.582l-.92 3.445h-.687V2.78c0-.437-.354-.792-.79-.792h-1.976c-.44 0-.793.354-.793.792v3.235h-.78l-1.243-3.507c-.116-.31-.412-.52-.746-.52h-2.305c-.268 0-.52.136-.664.363-.15.228-.17.512-.06.828l1.843 4.048-1.86 4.698c-.094.242-.06.516.087.732.148.215.392.344.65.344h2.306c.35 0 .655-.228.758-.562l1.043-3.44h.97v3.21c0 .437.353.79.79.79h1.976c.437 0 .79-.354.79-.79V9h.834l.767 3.387c.087.357.404.613.77.613h2.33c.252 0 .49-.12.64-.32.148-.202.193-.463.12-.705l-1.506-4.752zM40.217 2.417c-.004-.008-.012-.017-.018-.024-.024-.045-.058-.09-.095-.132-.008-.007-.013-.02-.02-.028-.046-.045-.095-.083-.15-.12-.01-.007-.02-.012-.036-.02-.046-.024-.09-.045-.14-.062l-.05-.013c-.062-.016-.128-.03-.194-.03h-1.98c-.06 0-.118.01-.177.022-.018.003-.03.012-.046.016-.04.013-.078.025-.115.045l-.056.026c-.03.02-.064.04-.095.066-.02.012-.033.024-.05.037-.028.032-.062.065-.088.098-.01.008-.017.017-.02.025l-3.27 4.613h-.042V2.78c0-.437-.355-.792-.792-.792h-1.975c-.438 0-.792.354-.792.792v9.427c0 .123.03.238.084.342 0 .008 0 .012.004.02s.013.018.017.02c.028.05.058.096.095.137.008.01.017.017.024.028.042.046.09.082.145.115.012.014.023.018.04.024.04.024.09.046.14.058.018.01.03.014.046.018.068.017.13.03.2.03h1.975c.063 0 .12-.01.178-.02.017-.006.033-.015.05-.02.037-.012.078-.023.115-.044l.05-.028c.032-.017.065-.037.1-.062.012-.013.028-.024.045-.04.032-.03.062-.063.086-.097.01-.013.02-.02.024-.024L36.7 8.12h.045v4.087c0 .438.354.793.79.793h1.98c.438 0 .786-.354.786-.793V2.78c0-.124-.027-.24-.076-.342-.003-.008-.003-.016-.007-.02zM51.225 1.99h-1.98c-.437 0-.786.353-.786.79V6h-2.887V2.78c0-.437-.354-.792-.793-.792h-1.973c-.438 0-.794.354-.794.792v9.427c0 .438.355.79.794.79h1.973c.438 0 .793-.353.793-.79V9h2.886v3.207c0 .438.35.79.786.79h1.98c.437 0 .79-.353.79-.79V2.78c0-.437-.354-.79-.79-.79zM11.084 9.994V2.78c0-.437-.354-.792-.792-.792H3.178c-.437 0-.792.354-.792.792L1.2 9.994H.802c-.433 0-.787.354-.787.79v3.425c0 .436.354.79.787.79h1.583c.438 0 .792-.354.792-.79v-1.147h5.537v1.146c0 .436.35.79.787.79h1.583c.437 0 .792-.354.792-.79v-3.425c0-.437-.356-.79-.793-.79zm-3.1.006l-3.417-.008.77-4.977h2.647V10zM59.28 1.79c-3.374 0-5.73 2.36-5.73 5.735 0 3.375 2.356 5.734 5.73 5.734 3.378 0 5.735-2.357 5.735-5.735 0-3.376-2.357-5.734-5.734-5.734zm0 8.192c-1.56 0-2.456-.896-2.456-2.458 0-1.562.895-2.457 2.457-2.457 1.563 0 2.458.895 2.458 2.457 0 1.564-.894 2.458-2.457 2.458z"
            />
          </svg>
          <p class="jino-domens jino-domens_white">домены</p>
        </div>
      </div>

      <div class="flex center">
        <p class="why-jino">Почему стоит выбрать «Джино»?</p>
      </div>

      <div class="flex center">
        <div class="col-10">
          <h2 class="bc3-title">
            «Джино» более 18 лет на рынке, имеет 270 000 довольных клиентов,
            собственную панель управления и многое другое.
          </h2>
        </div>
      </div>

      <div class="flex center">
        <div class="col-3 create-account create-account_3">
          <button class="create-account__btn">
            <p class="create-account__text">
              Создать аккаунт
            </p>
          </button>
        </div>
      </div>

      <div class="flex">
        <div class="col-12">
          <div class="bonus">
            <p class="bonus__text">
              Вы получите <span class="bonus__bold"> 1000 баллов</span> в
              системе лояльности <a href="" class="bonus__link">Джино.Плюсы</a>,
              зарегистрировавшись в течении
              <span class="bonus__bold"> 24 часов</span>
              после посещения данной страницы
            </p>
            <div class="bonus__1000">
              <p class="bonus__number">1000</p>

              <img class="bonus__img" src="@/assets/plus-bold.svg" alt="" />
            </div>
          </div>
        </div>
      </div>

      <div class="flex">
        <div class="col-12">
          <p class="rights">
            © «Джино», 2003–2017. «Джино» является зарегистрированным товарным
            знаком. Лицензия на телематические услуги связи № 97495 от
            09.03.2012. Правовая информация.
          </p>
        </div>
      </div>
    </div>

    <div class="navigation">
      <div class="navigation__circle" @click="scroll()"></div>
      <div class="navigation__circle" @click="scroll('background_one')"></div>
      <div class="navigation__circle navigation__circle_active"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "task1",
  data() {
    return {
      domen: "example.ru",
      successMsg: false,
      featuresTop: [
        { img: "businesscard", text: "Сайт-визитка" },
        { img: "dns", text: "Поддержка DNS" },
        { img: "certificate", text: "Сертификат о владении доменом" },
        { img: "autorenewal", text: "Автопродление" },
      ],
      featuresBottom: [
        {
          img: "cloud",
          text: "Облачное хранилище на 20 Гб",
        },
        { img: "freessl", text: "Бесплатный SSL-сертификат" },
        { img: "dnssec", text: "DNSSEC в один клик" },
        { img: "redirect", text: "Перенаправление" },
      ],
    };
  },

  methods: {
    scroll(el_1 = undefined, el_2 = undefined) {
      let top = 0;
      if (el_1) top = top + this.$refs[el_1].offsetHeight;
      if (el_2) top = top + this.$refs[el_2].offsetHeight;
      window.scrollTo({
        top: top,
        behavior: "smooth",
      });
    },
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=PT+Sans+Caption:wght@700&family=PT+Sans:wght@400;700&display=swap");

@mixin Breakpoint859 {
  @media (max-width: 859px) {
    @content;
  }
}

@mixin Breakpoint505 {
  @media (max-width: 505px) {
    @content;
  }
}

.background {
  width: 100%;
  background-size: cover;
  height: 843px;
  position: relative;

  @include Breakpoint859 {
    height: unset;
  }
  &_one {
    background-image: url("../assets/background1.jpg");
  }
  &_two {
    background-color: #fff;
  }
  &_three {
    height: unset;
    background-image: url("../assets/background2.jpg");
  }
}

.container {
  width: 90vw;
  margin: 0 auto;
  max-width: 1092px;
  min-width: 819px;

  @include Breakpoint859 {
    width: 100%;
    min-width: unset;
    padding: 0px 15px;
  }
}
.flex {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: space-between;
  position: relative;
}

.center {
  justify-content: center;
}
.jino {
  display: flex;
  align-items: center;
  position: absolute;
  top: 25px;
  left: 0px;
}
.jino-logo {
  width: 65px;
  height: 15px;
  &_white {
    fill: #ffffff;
  }
  &_red {
    fill: #b22725;
  }
}
.jino-domens {
  font-size: 16px;
  margin-left: 7px;
  font-family: "PT Sans";

  &_white {
    color: #ffffff;
    font-weight: 700;
  }

  &_black {
    color: #000000;
    font-weight: 400;
  }
}

.january {
  font-size: 12px;
  letter-spacing: 2px;
  color: #ffffff;
  font-weight: 700;
  font-family: "PT Sans";
  margin-top: 37px;
  text-align: center;
  @include Breakpoint505 {
    margin-top: 80px;
  }
}

.big-text {
  margin-top: 120px;
  font-size: 80px;
  color: #ffffff;
  font-weight: 700;
  font-family: "PT Sans Caption";
  text-align: center;

  @include Breakpoint859 {
    font-size: 50px;
    margin-top: 65px;
  }
  @include Breakpoint505 {
    font-size: 30px;
    margin-top: 39px;
  }
}

.form {
  width: 100%;
  margin-top: 65px;
  position: relative;

  @include Breakpoint859 {
    max-width: 400px;
    margin: 40px auto 0px auto;
  }

  @include Breakpoint505 {
    max-width: 240px;
    margin: 24px auto 0px auto;
  }

  &__input {
    width: 100%;
    height: 80px;
    background-color: #fff;
    border-radius: 7.5px;
    padding-left: 37px;
    font-size: 24px;
    color: #333333;
    font-weight: 400;
    font-family: "PT Sans";
    @include Breakpoint859 {
      height: 50px;
      padding-left: 23px;
      font-size: 15px;
      border-radius: 5px;
    }
    @include Breakpoint505 {
      height: 30px;
      padding-left: 14px;
      font-size: 14px;
      border-radius: 5px;
    }
  }
  &__btn {
    position: absolute;
    right: 15px;
    top: 14px;
    width: 157px;
    height: 52px;
    border-radius: 7.5px;
    background-color: #5f6062;
    display: flex;
    justify-content: center;
    align-items: center;
    &:hover {
      background-color: black;
    }
    @include Breakpoint859 {
      width: 98px;
      height: 32px;
      right: 10px;
      top: 9px;
      border-radius: 5px;
    }
    @include Breakpoint505 {
      width: 69px;
      height: 30px;
      right: 0;
      top: 0;
      border-radius: 5px;
      border-top-left-radius: 0px;
      border-bottom-left-radius: 0px;
    }
  }
  &__btn-text {
    font-size: 22px;
    color: #ffffff;
    font-weight: 400;
    font-family: "PT Sans";
    @include Breakpoint859 {
      font-size: 14px;
    }

    @include Breakpoint505 {
      font-size: 12px;
    }
  }
  &__result {
    background-color: rgb(51, 51, 51, 0.8);
    margin-top: -5px;
    padding-top: 20px;
    padding-bottom: 15px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 7.5px;
    @include Breakpoint859 {
      border-radius: 5px;
      padding-top: 15px;
      padding-bottom: 10px;
    }

    @include Breakpoint505 {
      padding-top: 10px;
      padding-bottom: 6px;
    }
  }
  &__msg {
    font-size: 16px;
    color: #f4f7fb;
    font-weight: 400;
    font-family: "PT Sans";
    @include Breakpoint859 {
      font-size: 12px;
      text-align: center;
    }
  }

  &__link {
    color: #77b53c;
    text-decoration: underline;
  }
}

.create-account {
  &_1 {
    margin-top: 35px;
    @include Breakpoint859 {
      margin-top: 22px;
    }
  }
  &_2 {
    margin-top: 50px;
    @include Breakpoint859 {
      margin-top: 32px;
      margin-bottom: 70px;
    }
    @include Breakpoint505 {
      margin-top: 19px;
      margin-bottom: 42px;
    }
  }

  &_3 {
    margin-top: 45px;
    @include Breakpoint859 {
      margin-top: 28px;
    }
  }
  &__btn {
    border-radius: 10px;
    background-color: #77b53c;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 55px;

    &:hover {
      background-color: black;
    }
    @include Breakpoint859 {
      border-radius: 6.5px;
      height: 34px;
    }

    @include Breakpoint505 {
      height: 24px;
      width: 100px;
    }
  }

  &__text {
    font-size: 24px;
    color: #ffffff;
    font-weight: 700;
    font-family: "PT Sans";
    @include Breakpoint859 {
      font-size: 15px;
    }

    @include Breakpoint505 {
      font-size: 12px;
    }
  }
}

.arrow {
  width: 26px;
  height: 50px;
  margin-top: 137px;
  cursor: pointer;
  @include Breakpoint859 {
    margin-top: 86px;
    margin-bottom: 80px;
  }

  @include Breakpoint505 {
    margin-top: 52px;
    margin-bottom: 48px;
    width: 16px;
    height: 30px;
  }
}

.navigation {
  height: 70px;
  position: absolute;
  right: 29px;
  top: calc(50% - 35px);
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  @include Breakpoint505 {
    display: none;
  }
  &__circle {
    width: 11px;
    height: 11px;
    border-radius: 11px;
    background-color: #ffffff;
    border: 1px solid #333333;
  }
  &__circle_active {
    background-color: #333333;
    border: 1px solid #ffffff;
  }
}

.you-get {
  margin-top: 103px;
  font-size: 35px;
  color: #333333;
  font-weight: 700;
  font-family: "PT Sans";
  text-align: center;
  @include Breakpoint859 {
    margin-top: 65px;
    font-size: 22px;
  }

  @include Breakpoint505 {
    margin-top: 70px;
    font-size: 18px;
  }
}

.featuresTop {
  margin-top: 72px;
  @include Breakpoint859 {
    flex-wrap: wrap;
    align-items: space-between;
    height: 300px;
    margin-top: 45px;
  }

  @include Breakpoint505 {
    margin-top: 27px;
    height: unset;
  }
}

.col-feature {
  @include Breakpoint859 {
    flex-basis: calc(100% / 2 - 0.5%) !important;
  }

  @include Breakpoint505 {
    flex-basis: 100% !important;
  }
}
.featuresBottom {
  margin-top: 30px;
  @include Breakpoint859 {
    flex-wrap: wrap;
    align-items: space-between;
    height: 300px;
    margin-top: 40px;
  }

  @include Breakpoint505 {
    margin-top: 24px;
    height: unset;
  }
}
.feature {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  @include Breakpoint505 {
    margin-top: 25px;
  }
  &__text {
    margin-top: 22px;
    font-size: 20px;
    line-height: 25px;
    color: #333333;
    font-weight: 400;
    font-family: "PT Sans";
    text-align: center;
  }
}

.features-description {
  position: relative;
  margin-top: 25px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 10px;
  background-color: #f7f7f7;
  border: 1px solid rgba(95, 96, 98, 0.5);
  @include Breakpoint859 {
    margin-top: 0px;
    border-radius: 6px;
    margin-right: 50px;
  }

  @include Breakpoint505 {
    margin-right: 0px;
    margin-top: 30px;
  }
  &__text {
    padding: 27px 43px;
    width: 100%;
    font-size: 16px;
    color: #333333;
    font-weight: 400;
    font-family: "PT Sans";
    @include Breakpoint859 {
      padding: 17px 27px;
    }

    @include Breakpoint505 {
      padding: 10px 16px;
      text-align: center;
    }
  }

  &__arror-wrapper {
    position: absolute;
    top: -22.5px;
    -moz-top: -30px;
    left: 0;
    z-index: 2;
    overflow: hidden;
    display: flex;
    justify-content: center;
    width: calc(100% / 4 - 0.75%);
    height: 46px;
    @include Breakpoint859 {
      display: none;
    }
  }

  &__arrow {
    margin-top: 6px;
    width: 30px;
    height: 30px;
    background-color: #f7f7f7;
    border-top: 1px solid rgba(95, 96, 98, 0.5);
    border-left: 1px solid rgba(95, 96, 98, 0.5);
    transform: rotate(45deg);
  }
}

.why-jino {
  margin-top: 104px;
  font-size: 35px;
  color: #ffffff;
  font-weight: 700;
  font-family: "PT Sans";
  text-align: center;
  @include Breakpoint859 {
    margin-top: 65px;
    font-size: 22px;
  }

  @include Breakpoint505 {
    margin-top: 69px;
    font-size: 18px;
  }
}

.bc3-title {
  width: 100%;
  margin-top: 98px;
  font-size: 50px;
  line-height: 60px;
  color: #ffffff;
  font-weight: 700;
  font-family: "PT Sans Caption";
  text-align: center;
  @include Breakpoint859 {
    margin-top: 61px;
    font-size: 31px;
    line-height: 37.5px;
  }

  @include Breakpoint505 {
    margin-top: 40px;
    font-size: 22px;
    line-height: 25px;
  }
}

.bonus {
  margin-top: 58px;
  width: 100%;
  height: 111px;
  border-radius: 5px;
  background-color: #df4a5e;
  padding: 0px 34px;
  display: flex;
  align-items: center;
  justify-content: space-between;

  @include Breakpoint859 {
    margin-top: 37px;
    height: unset;
    padding: 10px 15px;
    flex-direction: column;
  }

  @include Breakpoint505 {
    margin-top: 32px;
    padding: 6px 10px;
  }
  &__text {
    font-size: 22px;
    color: #ffffff;
    font-weight: 400;
    font-family: "PT Sans";
    line-height: 26px;
    margin-right: 70px;
    @include Breakpoint859 {
      font-size: 14px;
      line-height: 16px;
      margin-right: 0px;
      text-align: center;
    }

    @include Breakpoint505 {
      font-size: 12px;
      line-height: 14px;
    }
  }
  &__bold {
    color: #ffffff;
    font-weight: 700;
    font-family: "PT Sans";
  }
  &__link {
    color: #ffffff;
    text-decoration: underline;
  }
  &__1000 {
    border-left: 2px solid rgb(255, 255, 255, 0.3);
    padding-left: 37px;
    display: flex;
    justify-content: left;
    align-items: center;
    height: 63%;
    @include Breakpoint859 {
      border-left: none;
      padding-left: 0px;
      height: unset;
      margin-top: 5px;
    }
  }
  &__number {
    font-size: 50px;
    letter-spacing: 1.5px;
    color: #ffffff;
    font-weight: 700;
    font-family: "PT Sans Caption";
    margin-right: 10px;
    @include Breakpoint859 {
      font-size: 31px;
      margin-right: 6px;
    }

    @include Breakpoint505 {
      font-size: 22px;
      margin-right: 4px;
    }
  }
  &__img {
    width: 28px;
    height: 28px;
    filter: invert(1);
    @include Breakpoint859 {
      width: 17.5px;
      height: 17.5px;
    }

    @include Breakpoint505 {
      width: 10.5px;
      height: 10.5px;
    }
  }
}

.rights {
  margin: 50px 0px;
  font-size: 14px;
  line-height: 16px;
  color: rgb(255, 255, 255, 0.5);
  font-weight: 400;
  font-family: "PT Sans";
  @include Breakpoint859 {
    margin: 31px 0px;
    font-size: 12px;
    line-height: 14px;
    text-align: center;
  }

  @include Breakpoint505 {
    font-size: 10px;
    line-height: 12px;
  }
}

.col-1 {
  flex-basis: calc(100% / 12 - 1%);
}
.col-2 {
  width: calc(100% / 6 - 0.83%);
}
.col-3 {
  flex-basis: calc(100% / 4 - 0.75%);
}
.col-4 {
  flex-basis: calc(100% / 3 - 0.66%);
}
.col-6 {
  flex-basis: calc(100% / 2 - 0.5%);
}
.col-8 {
  flex-basis: calc(100% / 3 * 2 - 0.25%);
}
.col-10 {
  flex-basis: calc(100% / 6 * 5 - 0.16%);
}
.col-12 {
  width: 100%;
}
.mw {
  max-width: 210px;
}
</style>
