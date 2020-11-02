<template>
    <div class="row">
        <div class="col-6">
        <card
            type="pricing"
            class="card-primary"
            footer-classes="text-center mb-3 mt-3">
            <h1 class="card-title">pro</h1>
            <img class="card-img" src="https://demos.creative-tim.com/vue-black-dashboard-pro/img/card-primary.png" alt="Image" />
            <ul class="list-group">
            <li class="list-group-item">300 messages</li>
            <li class="list-group-item">150 emails</li>
            <li class="list-group-item">24/7 Support</li>
            </ul>
            <div class="card-prices">
            <h3 class="text-on-front"><span>$</span>95</h3>
            <h5 class="text-on-back">95</h5>
            <p class="plan">Professional plan</p>
            </div>
            <base-button slot="footer" round type="primary" class="btn-just-icon">
            Get started
            </base-button>
        </card>
        </div>
        <div class="col-6">
        </div>
    </div>
</template>

<script>
import {Card} from '@/components'
export default {
    components: {
        Card
    }
}
</script>