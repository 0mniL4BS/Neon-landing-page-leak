<template>
    <section
        class="pricing section"
        :class="[
            topOuterDivider && 'has-top-divider',
            bottomOuterDivider && 'has-bottom-divider',
            hasBgColor && 'has-bg-color',
            invertColor && 'invert-color'
        ]">
        <div class="container">
            <div
                class="pricing-inner section-inner"
                :class="[
                    topDivider && 'has-top-divider',
                    bottomDivider && 'has-bottom-divider'
                ]">
                <c-section-header :data="sectionHeader" tag="h1" class="center-content reveal-from-bottom" />
                <div
                    v-if="pricingSwitcher"
                    class="pricing-switcher center-content reveal-from-top"
                >
                    <c-switch
                        v-model="pricingSwitchOn"
                        right-label="Billed Annually">
                        Billed Monthly
                    </c-switch>
                </div>
                <div
                    class="tiles-wrap"
                    :class="[
                        pushLeft && 'push-left',
                    ]">
                    <div class="tiles-item reveal-from-right" data-reveal-delay="400">
                        <div class="tiles-item-inner">
                            <div class="pricing-item-content">
                                <div class="pricing-item-header pb-24 mb-24">
                                    <div class="pricing-item-price mb-4">
                                        <span class="pricing-item-price-currency h3">$</span>
                                        <span class="pricing-item-price-amount h1">{{pricingSwitchOn ? '27' : '34'}}</span>
                                        <span class="text-sm">/m</span>
                                    </div>
                                    <div class="text-xs text-color-low">
                                        Lorem ipsum is a common text
                                    </div>
                                </div>
                                <div class="pricing-item-features mb-40">
                                    <div class="pricing-item-features-title h6 text-xs text-color-high mb-24">
                                        What’s included
                                    </div>
                                    <ul class="pricing-item-features-list list-reset text-xs mb-32">
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li>Excepteur sint occaecat velit</li>
                                        <li>Excepteur sint occaecat velit</li>
                                    </ul>
                                </div>
                            </div>
                            <div class="pricing-item-cta mb-8">
                                <c-button tag="a" color="primary" wide href="#">Start free trial</c-button>
                            </div>
                        </div>
                    </div>

                    <div class="tiles-item reveal-from-bottom" data-reveal-delay="200">
                        <div class="tiles-item-inner">
                            <div class="pricing-item-content">
                                <div class="pricing-item-header pb-24 mb-24">
                                    <div class="pricing-item-price mb-4">
                                        <span class="pricing-item-price-currency h3">$</span>
                                        <span class="pricing-item-price-amount h1">{{pricingSwitchOn ? '47' : '54'}}</span>
                                        <span class="text-sm">/m</span>
                                    </div>
                                    <div class="text-xs text-color-low">
                                        Lorem ipsum is a common text
                                    </div>
                                </div>
                                <div class="pricing-item-features mb-40">
                                    <div class="pricing-item-features-title h6 text-xs text-color-high mb-24">
                                        What’s included
                                    </div>
                                    <ul class="pricing-item-features-list list-reset text-xs mb-32">
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li>Excepteur sint occaecat velit</li>
                                    </ul>
                                </div>
                            </div>
                            <div class="pricing-item-cta mb-8">
                                <c-button tag="a" color="primary" wide href="#">Start free trial</c-button>
                            </div>
                        </div>
                    </div>

                    <div class="tiles-item reveal-from-left" data-reveal-delay="400">
                        <div class="tiles-item-inner">
                            <div class="pricing-item-content">
                                <div class="pricing-item-header pb-24 mb-24">
                                    <div class="pricing-item-price mb-4">
                                        <span class="pricing-item-price-currency h3">$</span>
                                        <span class="pricing-item-price-amount h1">{{pricingSwitchOn ? '67' : '74'}}</span>
                                        <span class="text-sm">/m</span>
                                    </div>
                                    <div class="text-xs text-color-low">
                                        Lorem ipsum is a common text
                                    </div>
                                </div>
                                <div class="pricing-item-features mb-40">
                                    <div class="pricing-item-features-title h6 text-xs text-color-high mb-24">
                                        What’s included
                                    </div>
                                    <ul class="pricing-item-features-list list-reset text-xs mb-32">
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                        <li class="is-checked">Excepteur sint occaecat velit</li>
                                    </ul>
                                </div>
                            </div>
                            <div class="pricing-item-cta mb-8">
                                <c-button tag="a" color="primary" wide href="#">Start free trial</c-button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import { SectionTilesProps } from '@/utils/SectionProps.js'
import CSectionHeader from '@/components/sections/partials/SectionHeader.vue'
import CSwitch from '@/components/elements/Switch.vue'
import CButton from '@/components/elements/Button.vue'

export default {
  name: 'CPricing',
  components: {
    CSectionHeader,
    CSwitch,
    CButton
  },
  mixins: [SectionTilesProps],
  props: {
    pricingSwitcher: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      sectionHeader: {
        title: 'Engage Your Visitors with a beautiful template',
        paragraph: ''
      },
      pricingSwitchLabels: {
        type: 'Billing Period', // screen-reader text
        default: 'Billed Monthly',
        switchOn: 'Billed Annually'
      },
      pricingSwitchOn: true
    }
  }
}
</script>