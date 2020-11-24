<template>
  <div class="container">
    <div class="flex center">
      <div class="col-6">
        <h3 class="title">Подтверждение аккаунта</h3>
      </div>
    </div>
    <div class="flex center">
      <div class="col-6">
        <p class="text">
          Для подтверждения Вашего аккаунта Вам нужно заполнить все поля,
          подтвердить почтовый ящик и телефон, а также загрузить сканы ваших
          документов.
        </p>
      </div>
    </div>

    <div class="flex center">
      <div class="col-6 download">
        <div class="col-2">
          <img
            :src="require(`@/assets/${photo_photo}.svg`)"
            alt=""
            class="download__img"
          />
        </div>
        <div class="download__text">
          <label
            for="photo"
            class="download__btn"
            v-if="photo_status == '' || photo_status == 'decline'"
          >
            {{ photo_btn }}
          </label>

          <h5 class="download__btn" v-else>
            {{ photo_btn }}
          </h5>
          <input
            type="file"
            id="photo"
            class="input-file"
            accept=".png, .jpg, .jpeg"
            @change="photo_onFileSelected"
          />
          <p class="download__info">{{ photo_info }} {{ photo_size }}</p>
        </div>
        <div
          v-if="photo_status == 'success'"
          class="col-2 download__status status__success"
        >
          Проверено
        </div>
        <div
          v-if="photo_status == 'decline'"
          class="col-2 download__status status__decline"
        >
          Отклонено
        </div>
        <div
          v-if="photo_status == 'control'"
          class="col-3 download__status status__control"
        >
          Идёт проверка
        </div>
      </div>
    </div>
    <!--  -->
    <div class="flex center ">
      <div class="col-6 download download_last">
        <div class="col-2">
          <img
            :src="require(`@/assets/${registration_photo}.svg`)"
            alt=""
            class="download__img"
          />
        </div>
        <div class="download__text">
          <label
            for="registration"
            class="download__btn"
            v-if="registration_status == '' || registration_status == 'decline'"
          >
            {{ registration_btn }}
          </label>

          <h5 class="download__btn" v-else>
            {{ registration_btn }}
          </h5>
          <input
            type="file"
            id="registration"
            class="input-file"
            accept=".png, .jpg, .jpeg"
            @change="registration_onFileSelected"
          />
          <p class="download__info">
            {{ registration_info }} {{ registration_size }}
          </p>
        </div>
        <div
          v-if="registration_status == 'success'"
          class="col-2 download__status status__success"
        >
          Проверено
        </div>
        <div
          v-if="registration_status == 'decline'"
          class="col-2 download__status status__decline"
        >
          Отклонено
        </div>
        <div
          v-if="registration_status == 'control'"
          class="col-3 download__status status__control"
        >
          Идёт проверка
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "task2",

  data() {
    return {
      photo_photo: "upload",
      photo_btn: "Загрузить скан страницы с фотографией",
      photo_info: "Размер файла не более 5Мб",
      photo_size: "",
      photo_status: "",

      registration_photo: "upload",
      registration_btn: "Загрузить скан страницы с пропиской",
      registration_info: "Размер файла не более 5Мб",
      registration_size: "",
      registration_status: "",
      isValid: () => {
        return Math.random() <= +0.5;
      },
    };
  },
  methods: {
    photo_onFileSelected(event) {
      let file = event.target.files[0];
      if (file.size > 5000000) return false;

      this.photo_status = "control";

      this.photo_photo = "wait";
      this.photo_btn = "Файл загружен";
      this.photo_info = file.name;
      this.photo_size = this.fileSizeFilter(file.size);

      setTimeout(this.photo_control, 3000);
    },

    photo_control() {
      if (this.isValid()) {
        this.photo_status = "success";
        this.photo_photo = "ok";
        this.photo_btn = "Страница с фотографией";
      } else {
        this.photo_status = "decline";
        this.photo_photo = "upload";
        this.photo_btn = "Загрузить скан страницы с фотографией";
        this.photo_info = "Размер файла не более 5Мб";
        this.photo_size = "";
      }
    },

    registration_onFileSelected(event) {
      let file = event.target.files[0];
      if (file.size > 5000000) return false;

      this.registration_status = "control";
      this.registration_photo = "wait";
      this.registration_btn = "Файл загружен";
      this.registration_info = file.name;
      this.registration_size = this.fileSizeFilter(file.size);

      setTimeout(this.registration_control, 1000);
    },

    registration_control() {
      if (this.isValid()) {
        this.registration_status = "success";
        this.registration_photo = "ok";
        this.registration_btn = "Страница с пропиской";
      } else {
        this.registration_status = "decline";
        this.registration_photo = "upload";
        this.registration_btn = "Загрузить скан страницы с пропиской";
        this.registration_info = "Размер файла не более 5Мб";
        this.registration_size = "";
      }
    },
    fileSizeFilter(fileSize) {
      let filtered = fileSize
        .toString()
        .slice(0, fileSize.toString().length - +3);
      if (filtered.length <= 3) return `(${filtered} Кб)`;
      filtered = filtered.slice(0, filtered.length - +3);
      return `(${filtered} Мб)`;
    },
  },
};
</script>

<style scoped lang="scss">
@import url("https://fonts.googleapis.com/css2?family=PT+Sans+Caption:wght@700&family=PT+Sans:wght@400;700&display=swap");

.title {
  margin-top: 200px;
  font-size: 20px;
}

.text {
  margin-top: 20px;
  font-size: 14px;
  line-height: 16px;

  color: rgb(157, 157, 157);
}

.download {
  margin-top: 30px;
  display: flex;
  justify-content: left;
  align-items: center;
  &__img {
    width: 60%;
    background-color: #fff;
    padding: 7px;
  }

  &__text {
    display: flex;
    flex-direction: column;
  }
  &__btn {
    font-size: 16px;
    width: 100%;
    cursor: pointer;
    &:hover {
      text-decoration: underline;
    }
  }
  &__info {
    margin-top: 8px;
    font-size: 14px;
    color: rgb(157, 157, 157);
  }

  &__status {
    text-align: right;
    font-size: 14px;
    margin-top: 9px;
    align-self: flex-start;
    margin-left: auto;
  }

  &_last {
    margin-bottom: 70px;
  }
}

.status {
  &__success {
    color: rgb(117, 162, 67);
  }
  &__control {
    color: rgb(166, 166, 166);
  }
  &__decline {
    color: rgb(214, 36, 33);
  }
}

.input-file {
  display: none;
}
* {
  font-family: "PT Sans";
  font-weight: 400;
}
.container {
  width: 90vw;
  margin: 0 auto;
  margin-bottom: 50px;
  max-width: 1092px;
  min-width: 819px;
  background-color: #f8f8f8;
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
</style>
