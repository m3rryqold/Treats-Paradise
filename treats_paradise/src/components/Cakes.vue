
<template>
    <b-container>
        <div v-if="cakes.length">
            <b-row>
                <div v-bind:key="cake.index" v-for="cake in cakes">
                    <b-col l="4">
                        <b-card
                            v-bind:img-src="`http://localhost:1337${cake.product_image[0].formats.thumbnail.url}`"
                            v-bind:title="cake.title"
                            img-alt="Black Forest"
                            img-top
                            tag="article"
                            style="max-width: 20rem;"
                            class="mb-2"
                            >
                            <b-card-text>{{`${cake.description}`}}</b-card-text>
                            <span>
                                <strong>Price: ${{`${cake.price}`}}</strong>
                            </span>
                            <b-button @click="placeOrder" variant="primary">Order Cake</b-button>
                        </b-card>
                    </b-col>
                </div>
            </b-row>
        </div>
        <div v-else>
            <p>Cakes {{ `${cakes.length}` }}</p>
            <h5>Fetching Cakes...</h5>
        </div>
    </b-container>
</template>

<script>
export default {
    data() {
        return {
            cakes: [],
        }
    },
    mounted() {
        console.log("inside mounted")
        fetch("http://localhost:1337/products")
            .then((res)=>res.json())
            .then((data) => {
                this.cakes = data;
            })
    }
}
</script>