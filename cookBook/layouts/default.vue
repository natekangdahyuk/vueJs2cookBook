<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item v-for="item in allowed_menus" :key="item.title">
          <template v-if="item.children">
            <v-list-group v-model="item.childrenActive">
              <template v-slot:activator>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </template>
              <v-list-item v-for="subItem in item.children" :key="subItem.title" :to="subItem.to">
                <v-list-item-content>{{ subItem.title }}</v-list-item-content>
              </v-list-item>
            </v-list-group>
          </template>
          <template v-else>
            <v-list-item :to="item.to">
              <v-list-item-content>{{ item.title }}</v-list-item-content>
            </v-list-item>
          </template>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar :clipped-left="clipped" fixed app>
      <!-- 앱 바 내용 -->
        <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
    </v-app-bar>

    <v-main>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'default-menu',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      companyLogoAsset: require('../assets/etoylab_CI_Mono.png'),
      allowed_menus: [
        {
          title: '쿡북1장',
          icon: 'mdi-home',
          childrenActive: false,
          children: [
            { title: '1.1.v-for', to: '/devBook/chapter1/1-1_v-for_CountDown'},
            { title: '1.2.v-model_inBtn', to: '/devBook/chapter1/1-2_v-model_inputText' },
            { title: '1.3.v-model_delBtn', to: '/devBook/chapter1/1-3_v-model_DelButton' },
            { title: '1-4.filter', to: '/devBook/1-4.filter' },
          ]
        },
        {
          title: '쿡북2장',
          icon: 'mdi-account',
          childrenActive: false,
          children: [
            { title: '2-1_computed_setter', to: '/devBook/chapter2/2-1_computed_setter'},
            { title: '2-2_computed_filter', to: '/devBook/chapter2/2-2_computed_filter'},
            { title: '2-3_computted_sort', to: '/devBook/chapter2/2-3_computted_sort'},
            { title: '2-4_accountingJs', to: '/devBook/chapter2/2-4_accountingJs'},
            { title: '2-5_moment', to: '/devBook/chapter2/2-5_moment'},
            { title: '2-6_cssChange', to: '/devBook/chapter2/2-6_cssChange'},
            { title: '2-7_transition_show', to: '/devBook/chapter2/2-7_transition_show'},
            { title: '2-8_transition_hide', to: '/devBook/chapter2/2-8_transition_hide'},
            { title: '2-9_v-html', to: '/devBook/chapter2/2-9_v-html'},
            { title: '2-10_component', to: '/devBook/chapter2/2-10_component'},
            { title: '2-11_checkbox', to: '/devBook/chapter2/2-11_checkbox'},
            { title: '2-12_radiobox', to: '/devBook/chapter2/2-12_radiobox'},
            { title: '2-13_radiobox_animalBuy', to: '/devBook/chapter2/2-13_radiobox_animalBuy'},
            { title: '2-14_select_country', to: '/devBook/chapter2/2-14_select_country'},
            { title: '2-15_select_multiAnimals', to: '/devBook/chapter2/2-15_select_multiAnimals'},
          ]
        },
        {
          title: '쿡북3장',
          icon: 'mdi-account',
          childrenActive: false,
          children: [
            { title: '3-1_animated_css', to: '/devBook/chapter3/3-1_animated_css'},
            { title: '3-2_animated_js', to: '/devBook/chapter3/3-2_animated_js'},
            { title: '3-3_fadein', to: '/devBook/chapter3/3-3_fadein'},
            { title: '3-4_transition_key', to: '/devBook/chapter3/3-4_transition_key'},
            { title: '3-5_transition-caroset', to: '/devBook/chapter3/3-5_transition-caroset'},
            { title: '3-6_transition-group', to: '/devBook/chapter3/3-6_transition-group'},
            { title: '3-7_transition-group-leave-active', to: '/devBook/chapter3/3-7_transition-group-leave-active'},
            { title: '3-8_transition-group_splicev', to: '/devBook/chapter3/3-8_transition-group_splicev'},
            { title: '3-9_transition_component', to: '/devBook/chapter3/3-9_transition_component'},
          ]
        },
        {
          title: '쿡북4장',
          icon: 'mdi-database',
          childrenActive: false,
          children: [
            { title: '4-1_com_basic', to: '/devBook/chapter4/4-1_com_basic'},
            { title: '4-2_com_props', to: '/devBook/chapter4/4-2_com_props'},
            { title: '4-3_com_communication', to: '/devBook/chapter4/4-3_com_communication'},
            { title: '3-4_transition_key', to: '/devBook/chapter4/3-4_transition_key'},
            { title: '3-5_transition-caroset', to: '/devBook/chapter4/3-5_transition-caroset'},
            { title: '3-6_transition-group', to: '/devBook/chapter4/3-6_transition-group'},
            { title: '3-7_transition-group-leave-active', to: '/devBook/chapter4/3-7_transition-group-leave-active'},
            { title: '3-8_transition-group_splicev', to: '/devBook/chapter4/3-8_transition-group_splicev'},
            { title: '3-9_transition_component', to: '/devBook/chapter4/3-9_transition_component'},
          ]
        },
      ],
      miniVariant: false,
    } // data () - return
  },

}
</script>
<style>

/*.v-text-field.v-input--dense:not(.v-select):not(.v-text-field--filled):not(.v-text-field--outlined) .v-label {*/
/*  top: -16px !important;*/
/*}*/

.v-text-field.v-text-field--filled > .v-input__control > .v-input__slot
{
  min-height: auto;
  height: 48px;
}

.v-text-field:not(.v-text-field--filled):not(.v-text-field--filled):not(.v-text-field--outlined) .v-label
{
  font-size: 14px;
  transition: none;
  top: -14px !important;
}

.v-text-field.v-text-field--filled .v-label
{
  font-size: 14px;
  transition: none;
  top: 2px !important;
}

.v-input--radio-group .v-label
{
  font-size: 14px;
}

/* Select Box 용 */
.v-select.v-input--is-label-active .v-label
{
  font-size: 18px;
  transition: none;
  /*top: 2px;*/
}
</style>