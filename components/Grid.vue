<template lang="pug">
  v-card.mb-5
    v-table-overflow
      table.table
        caption.mt-3
          strong Material Design Viewport Breakpoints
        thead
          tr.text-xs-left
            th Device
            th Types
            th Range
        tbody
          tr
            td
              v-icon.mr-3 phone_iphone
              span Extra small
            td small to large handset
            td &lt; 600px
          tr
            td
              v-icon.mr-3 tablet
              span Small
            td small to medium tablet
            td 600px &gt; &lt; 960px
          tr
            td
              v-icon.mr-3 laptop
              span Medium
            td large tablet to laptop
            td 960px &gt; &lt; 1264*
          tr
            td
              v-icon.mr-3 desktop_windows
              span Large
            td desktop
            td 1264 &gt; &lt; 1904px*
          tr
            td
              v-icon.mr-3 tv
              span Extra large
            td 4k and ultra-wides
            td &gt; 1904px*
        tfoot
          tr
            td(colspan="3").text-xs-center
              small
                em.grey--text * -16px on Desktop
</template>
