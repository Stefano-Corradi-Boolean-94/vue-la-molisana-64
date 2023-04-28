
<script>
import { mainMenu, footerMenu } from '../data/menus';

export default {
  name:'Footer',
  data() {
    return {
      mainMenu,
      footerMenu
    }
  },
}
</script>

<template>
  <footer>
    <div class="top container">
      <div class="col">
        <img src="/logo-molisana.png" alt="Logo Molisana">
      </div>
      <div class="col">
        <h4>MENU</h4>
        <nav>
          <ul>
            <li 
              v-for="(link, index) in mainMenu"
              :key="index">
              <a :class="{'active' : link.isActive}" :href="link.href">{{ link.text }}</a>
            </li>
          </ul>
        </nav>
      </div>
      <div class="col">
        <h4>PASTIFICIO</h4>
        <nav>
          <ul>
            <li 
              v-for="(link, index) in footerMenu.pastificio"
              :key="index">
              <a :class="{'active' : link.isActive}" :href="link.href">{{ link.text }}</a>
            </li>
          </ul>
        </nav>
      </div>
      <div class="col">
        <h4>Prodotti</h4>
        <nav>
          <ul>
            <li 
              v-for="(link, index) in footerMenu.prodotti"
              :key="index">
              <a :class="{'active' : link.isActive}" :href="link.href">{{ link.text }}</a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
    <div class="bottom">
      <img src="../assets/img/footer.jpg" alt="Montagne">
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@use '../scss/general/variables' as *;

footer{
  padding-top: 3rem;
  .top{
    display: flex;
    .col{
      width: 20%;
      &:first-child{
        width: 40%;
      }
      h4{
        margin-bottom: 1rem;
        text-transform: uppercase;
      }
      li{
        margin-bottom: .5rem;
        a{
          font-size: .9rem;
          color: $link-color;
          &:hover{
            text-decoration: underline;
          }
        }
      }
    }
  }
}

</style>