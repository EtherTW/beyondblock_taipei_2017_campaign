<template>
  <section class="staff">
    <div class="title">
      <i class="title__icon"></i>
      <h1 class="title__wording">{{$t('staffTitle')}}</h1>
    </div>

    <div class="staff__box">
      <div class="staff__img" v-for="(role, index) in $t('staff')" :key="role.name + index">
        <img :src="role.img">
        <a v-if="role.url" :href="role.url" target="_blank">
          <span>{{role.name}} - {{role.duty}}</span>
        </a>
        <a v-else :href="role.url" target="_blank">
          <span>{{role.name}} - {{role.duty}}</span>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'staff'
}
</script>

<style scoped lang="scss">
.staff {
  &__box {
    margin: 0 auto;
    width: 740px;
  }
  &__img {
    display: inline-block;
    margin: 24px;
    height: 135px;
    width: 135px;
    background: #D8D8D8;
    border: 3px solid #50E3C2;
    border-radius: 50%;
    position: relative;

    img {
      border-radius: 50%;
      width: 100%;
    }

    span {
      display: block;
      border-radius: 50%;
      background: #000;
      opacity: 0;
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0px;
      left: 0px;
      width: 100%;
      z-index: 100;
      color: #FFF;
      text-align: center;
      line-height: 129px;
      transition: 0.5s;
      font-size: 0.7rem;
    }

    span:hover {
      opacity: 0.7;
    }

    a {
      cursor: pointer;
    }
  }
}

@media only screen and (max-width: 767px) {
  .staff__box {
    width: 576px;
    padding: 5px;
  }
}

@media only screen and (max-width: 575px) {
  .staff__box {
    width: 375px;
    padding: 0px;
  }

  .staff__logo {
    display: none;
  }
}
</style>
