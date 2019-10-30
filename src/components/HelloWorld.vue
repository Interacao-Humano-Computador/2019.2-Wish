<template>
    <v-container>
        <v-row style="max-width: 1200px; margin: auto">
            <template v-for="n in 10" >
                <v-col cols="12" sm="6" md="4" lg="3" :key="n">
                    <CardProduct 
                        img="https://contestimg.wish.com/api/webimage/5d530f33538bd178f3ca4ed7-0-feed?cache_buster=f02fe347bf324e1f51a4156b8a50d3df&cozy=1"
                        value="R$ 50,00"
                        nonvalue="R$ 200,00"/>
                </v-col>
                <v-col cols="12" sm="6" md="4" lg="3" :key="n">
                    <CardProduct 
                        img="https://contestimg.wish.com/api/webimage/5d1b3b26136dca0a8f73ec28-0-feed?cache_buster=b9897f1238cd4b23afa9179872bbc87c&cozy=1"
                        value="R$ 48,00"
                        nonvalue="R$ 305,00"/>
                </v-col>
                <v-col cols="12" sm="6" md="4" lg="3" :key="n">
                    <CardProduct 
                        img="https://contestimg.wish.com/api/webimage/5d5a37de1e1d981d24fe02b0-0-feed?cache_buster=2a24fbacbc06b5f29572fd41b2403442&cozy=1"
                        value="R$ 15,00"
                        nonvalue="R$ 50,00"/>
                </v-col>
                <v-col cols="12" sm="6" md="4" lg="3" :key="n">
                    <CardProduct 
                        img="https://contestimg.wish.com/api/webimage/5d7b96ca9c40b0162a9dbac7-0-feed?cache_buster=fde871fa667a348b1bc184e75057ce7f&cozy=1"
                        value="R$ 302,00"
                        nonvalue="R$ 1.200,00"/>
                </v-col>
                <v-col cols="12" sm="6" md="4" lg="3" :key="n">
                    <CardProduct 
                        img="https://contestimg.wish.com/api/webimage/5d71a5109c80e72d17d04090-0-feed?cache_buster=b4351e890183c9c686e50051da7eac1a&cozy=1"
                        value="R$ 6,00"
                        nonvalue="R$ 37,00"/>
                </v-col>
            </template>
        </v-row>
        
    </v-container>
</template>

<script>
import CardProduct from './CardProduct'

export default {
    data: () => ({}),
    components: {
        CardProduct
    }
};
</script>
