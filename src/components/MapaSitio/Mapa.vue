<template>
  <div class="mapa-sitio">
    <p class="title is-1 has-text-weight-bold">
      <b-icon icon="sitemap-outline" size="is-large" type="is-primary">
      </b-icon>
      Mapa del Sitio
    </p>
    <div class="container text-center"
      style="text-align: center; height: 5rem; margin-bottom: 5rem;display: flex; justify-content: center;">
      <div class="row" style="width: 5cm; text-align: center; height: 1cm;">
        <div class="col"
          style="border: 2px solid #B197FC; border-radius: 8px; box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); text-align: center;">
          <b-icon icon="home"></b-icon>
          <hr>
          <b-button type="is-primary" style="margin-bottom: 1rem;">
            <router-link to="/" class="home-button" style="text-decoration: none; color: #333;">Inicio</router-link>
          </b-button>
        </div>
      </div>
    </div>
    <div class="container text-center"
      style="text-align: center; height: 5rem; margin-bottom: 5rem;display: flex; justify-content: center;">
      <div class="row" style="display: flex; justify-content: center;">
        <div style="margin-right: 1rem;">
          <div
            style="border: 2px solid #B197FC; border-radius: 8px; box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); text-align: center; width: 4cm;">
            <b-icon icon="food-fork-drink"></b-icon>
            <hr>
            <b-button type="is-primary" style="margin-bottom: 1rem;">
              <router-link to="/insumos" style="text-decoration: none; color: #333;">Alimentos</router-link>
            </b-button>
          </div>
        </div>
        <div style="margin-right: 1rem;">
          <div
            style="border: 2px solid #B197FC; border-radius: 8px; box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); text-align: center; width: 4cm;">
            <b-icon icon="order-bool-ascending-variant"></b-icon>
            <hr>
            <b-button type="is-primary" style="margin-bottom: 1rem;">
              <router-link to="/realizar-orden" style="text-decoration: none; color: #333;">Ordenar</router-link>
            </b-button>
          </div>
        </div>
        <div style="margin-right: 1rem;">
          <div
            style="border: 2px solid #B197FC; border-radius: 8px; box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); text-align: center; width: 4cm;">
            <b-icon icon="archive-outline"></b-icon>
            <hr>
            <b-button type="is-primary" style="margin-bottom: 1rem;">
              <router-link to="/categorias" style="text-decoration: none; color: #333;">Categorías</router-link>
            </b-button>
          </div>
        </div>
        <div style="margin-right: 1rem;">
          <div
            style="border: 2px solid #B197FC; border-radius: 8px; box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); text-align: center; width: 4cm;">
            <b-icon icon="account-group"></b-icon>
            <hr>
            <b-button type="is-primary" style="margin-bottom: 1rem;">
              <router-link to="/usuarios" style="text-decoration: none; color: #333;">Usuarios</router-link>
            </b-button>
          </div>
        </div>
        <div style="margin-right: 1rem;">
          <div
            style="border: 2px solid #B197FC; border-radius: 8px; box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); text-align: center; width: 4cm;">
            <b-icon icon="cash-register"></b-icon>
            <hr>
            <b-button type="is-primary" style="margin-bottom: 1rem;">
              <router-link to="/reporte-ventas" style="text-decoration: none; color: #333;">Ventas</router-link>
            </b-button>
          </div>
        </div>
        <div style="margin-right: 1rem;">
          <div
            style="border: 2px solid #B197FC; border-radius: 8px; box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); text-align: center; width: 4cm;">
            <b-icon icon="application-cog-outline"></b-icon>
            <hr>
            <b-button type="is-primary" style="margin-bottom: 1rem;">
              <router-link to="/configurar" style="text-decoration: none; color: #333;">Configurar</router-link>
            </b-button>
          </div>
        </div>
        <div>
          <div
            style="border: 2px solid #B197FC; border-radius: 8px; box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); text-align: center; width: 4cm;">
            <b-icon icon="sitemap-outline"></b-icon>
            <hr>
            <b-button type="is-primary" style="margin-bottom: 1rem;">
              <router-link to="/mapa" class="home-button" style="text-decoration: none; color: #333;">Mapa del
                Sitio</router-link>
            </b-button>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'MapaSitio'
}
</script>

<style scoped>
.mapa-sitio {
  text-align: left;
}
</style>