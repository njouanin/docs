<template lang="pug">
  doc-view#faq-view
    v-layout(row wrap)
      v-flex(xs12 sm8 md12)
        section-def
          dt(slot="title") Frequently asked questions
          dd(slot="desc") Stuck on a particular problem? Check some of these common gotchas before creating a ticket. If you still cannot find what you are looking for, submit an <a href="https://github.com/vuetifyjs/vuetify/issues/new" target="_blank" rel="noopener">issue</a> on github or ask the community in <a href="https://chat.vuetifyjs.com" target="_blank" rel="noopener">discord</a>.
      ad
    section#frequently-asked-questions
      v-expansion-panel(expand).mb-5
        v-expansion-panel-content(v-for="(faq, i) in faqs" v-bind:key="i")
          div(slot="header").pr-5
            strong Question: &nbsp;
            span(v-html="faq.q") 
          v-divider
          v-card.grey.lighten-4
            v-card-text
              strong Answer: &nbsp;
              div(v-html="faq.a")

      div.text-xs-center
        div.mb-3 Have something that you think belongs here?
        v-btn(outline success round href="https://chat.vuetifyjs.com" target="_blank" rel="noopener") Let us know
</template>

<script>
  export default {
    data: () => ({
      faqs: [
        {
          q: `My application does not look correct`,
          a: `Vuetify requires the use of the <code>v-app</code> component. It should wrap your entire application and is the center point for much of the framework functionality. If for whatever reason you cannot use this element, you can mimic it from attributes and classes. Set the <code>data-app</code> attribute to true on the highest element available (not including body), and the <strong>application application--{light|dark}</strong> classes.`
        },
        {
          q: `The Dark or Light theme are not working.`,
          a: `Vuetify requires a mounting point in order to perform tasks such as theme styling. Ensure that you have a <code>v-app</code> wrapping your application. In the event that this is not possible, for whatever reason, you can mimic its behavior by applying <strong>data-app</strong> and <strong>class="application application--light (or dark)</strong> to the highest element that you can within your application.`
        },
        {
          q: `Menu/Dialog/Navigation drawer are not opening properly.`,
          a: `Ensure that your components are wrapped with a <code>v-app</code> element. If you are using an element to activate the component that is not placed into the <kbd>activator</kbd> slot, ensure that you stop propagation of the click event. These components utilize the <code>v-outside-click</code> directive and will immediately close.`
        },
        {
          q: `The scrollbar is showing even though my content is not overflowing vertically.`,
          a: `Vuetify by default turns on the html scrollbar. This is a design choice and has been debated numerous times. There are pros and cons to having and not having it and as of now, the vote is in favor of leaving it as is. If you wish to disable this functionality, simply add <code>html { overflow-y: auto }</code> to your style file.`
        }
      ]
    })
  }
</script>

<style lang="stylus">
  #faq-view
    .expansion-panel__header
      > div
        overflow: hidden
        text-overflow: ellipsis
        white-space: nowrap
</style>
