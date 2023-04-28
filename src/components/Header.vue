
<script>
import { mainMenu } from '../data/menus'

export default {
  name:'Header',
  data(){
    return{
      mainMenu
    }
  }
}
</script>

<template>
  <header>
    <div class="logo">
      <!-- l'immagine è in public quindi percoso assoluto  -->
      <img src="/logo-molisana.png" alt="Logo Molisana">
    </div>
    <nav>
      <ul>

        <!-- ricordarsi di metter il bid della key passando un parametro univoco  -->
        <li 
          v-for="(link, index) in mainMenu"
          :key="index">
          <a :class="{'active' : link.isActive}" :href="link.href">{{ link.text }}</a>
        </li>

      </ul>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
@use '../scss/general/variables' as *;
@use '../scss/general/mixin' as *;

header{
  text-align: center;
  .logo{
    margin-bottom: 2rem;
  }
  ul{
    @include centerFlex('horizontal');
    margin-bottom: 2rem;
    a{
      display: inline-block;
      padding: 1rem;
      text-transform: capitalize;
      color: $link-color;
      font-weight: 600;
      &:hover,
      &.active{
        background-color: lighten($primary-color, 65%);
      }
    }
  }
}

</style>