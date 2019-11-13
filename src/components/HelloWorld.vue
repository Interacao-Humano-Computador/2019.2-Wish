<template>
    <v-container>
        <v-row style="max-width: 1200px; margin: auto">
            <template v-for="n in 6" >
                <v-col cols="12" sm="6" md="4" lg="3" :key="n + Math.random()">
                    <CardProduct
                        @activeDialog="activeDialogLocal(img1,text1 )" 
                        :img="img1"
                        value="R$ 50,00"
                        :description="text1"
                        nonvalue="R$ 200,00"/>
                </v-col>
                <v-col cols="12" sm="6" md="4" lg="3" :key="n + Math.random()">
                    <CardProduct
                        @activeDialog="activeDialogLocal(img2,text2 )" 
                        :img="img2"
                        value="R$ 48,00"
                        :description="text2"
                        nonvalue="R$ 305,00"/>
                </v-col>
                <v-col cols="12" sm="6" md="4" lg="3" :key="n + Math.random()">
                    <CardProduct
                        @activeDialog="activeDialogLocal(img3,text3 )" 
                        :img="img3"
                        value="R$ 15,00"
                        :description="text3"
                        nonvalue="R$ 50,00"/>
                </v-col>
                <v-col cols="12" sm="6" md="4" lg="3" :key="n + Math.random()">
                    <CardProduct
                        @activeDialog="activeDialogLocal(img4,text4 )" 
                        :img="img4"
                        value="R$ 302,00"
                        :description="text4"
                        nonvalue="R$ 1.200,00"/>
                </v-col>
                <v-col cols="12" sm="6" md="4" lg="3" :key="n + Math.random()">
                    <CardProduct
                        @activeDialog="activeDialogLocal(img5,text5)" 
                        :img="img5"
                        value="R$ 6,00"
                        :description="text5"
                        nonvalue="R$ 37,00"/>
                </v-col>
            </template>
        </v-row>
        <div class="carrinho" :class="minimizeCarrinho? 'minimize': ''" v-if="carrinhoItens > 0">
            <div class="headercarrinho">
                <v-btn
                    @click="minimizeCarrinho = !minimizeCarrinho"
                    icon>
                    <v-icon
                        color="#2fb7ec">
                        {{minimizeCarrinho?'mdi-cart-outline' : 'mdi-arrow-right'}}
                    </v-icon>
                </v-btn>
                <p>Carrinho</p>
                <v-btn
                    @click="dialog2 = true"
                    icon>
                    <v-icon
                        color="#2fb7ec">
                        mdi-cart-remove
                    </v-icon>
                </v-btn>
            </div>
            <div class="carrinho__item" v-for="(item, index) in carrinho" :key="index">
                <img :src="item.img" alt="">
                <p>{{item.text}}</p>
            </div>
            <v-btn
                depressed=""
                large
                color="#2fb7ec"
                class="white--text text-regular mt-auto ma-3"
                @click="routeTo('/carrinho')"
                style="font-weight: bold; font-size: 14px; text-transform: initial; letter-spacing: 0px;">
                Ver carrinho
            </v-btn>
        </div>
        <v-dialog
            max-width="1200px"
            v-model="dialog"
            class="dialog">
            <div class="content">
                <div class="d-flex">
                    <v-tabs class="pl-4">
                        <v-tab>
                            Visão geral
                        </v-tab>
                        <v-tab>
                            Produtos relacionados
                        </v-tab>
                    </v-tabs>
                    <v-spacer></v-spacer>
                    <v-btn
                    icon=""
                    class="mr-4 mt-2"
                    @click="dialog = false">
                        <v-icon>mdi-close</v-icon>
                    </v-btn>
                </div>
               

                <v-row no-gutters>
                    <v-col cols="8" class="custom-padding text-center">
                        <img :src="dialogImg" alt="" class="bigimg">
                        <hr class="hr">

                        <h3 class="text-left mt-6 mb-3">Description</h3>

                        <p class="text-left mb-0">
                            Description Capacity:128gb(3Pcs)
                        </p>
                        <p class="text-left mb-0">
                            Plug and Play 
                        </p>
                        <p class="text-left mb-0">
                            Dual USB 3.0 Micro-USB and USB A connectors on each end 
                        </p>
                        <p class="text-left mb-0">
                            Work as normal Flash Disk User can use this device when connect to PC and Notebook No need install any software.
                        </p>
                        <p class="text-left mb-0">
                            Compatibility:
                        </p>
                        <p class="text-left mb-0">
                            Android Smartphone/ Tablet with standard micro USB port
                            Support OTG function
                            V 2.0/3.0 Micro USB port (can&#39;t be used on iPhone or iPad ) 
                            Package Included: 128gb(3Pcs)
                        </p>
                    </v-col>
                    <v-col cols=4 class="pa-0">
                        <div class="boxDialog">
                            <p>{{dialogText}}</p>
                            
                            <div class="d-flex">
                                <v-icon size="20" color="#2fb7ec">mdi-star</v-icon>
                                <v-icon size="20" color="#2fb7ec">mdi-star</v-icon>
                                <v-icon size="20" color="#2fb7ec">mdi-star</v-icon>
                                <v-icon size="20" color="#2fb7ec">mdi-star</v-icon>
                                <v-icon size="20" color="#d4e3eb">mdi-star</v-icon>

                                <p style="color: #2fb7ec; font-size: 14px;" class="mb-0 ml-3">(525 avaliações)</p>
                            </div>

                            <h2>R$31 <span style="text-decoration: line-through;">R$232</span></h2>
                            
                            <p class="mb-1 mt-2">Selecione a capacidade:</p>
                            <v-select
                                :items="items"
                                label=""
                                outlined>
                            </v-select>

                            <v-btn
                                block=""
                                depressed=""
                                large=""
                                color="#2fb7ec"
                                class="white--text text-regular"
                                @click="addToCarrinho(dialogImg,dialogText)"
                                style="font-weight: bold; font-size: 18px;">
                                Adicionar ao carrinho
                            </v-btn>
                        </div>
                    </v-col>
                </v-row>
            </div>
        </v-dialog>

        <v-dialog v-model="dialog2" max-width="500" >
            <v-card class="login-box">
                <div class="d-flex align-center" style="width: 100%;">
                    <v-card-title class="title px-0">Atenção!</v-card-title>
                    
                    <v-btn
                        icon=""
                        class="ml-auto"
                        @click="dialog2 = false">
                        <v-icon>mdi-close</v-icon>
                    </v-btn>
                </div>

                <p>Tem certeza que deseja limapr o carrinho?</p>
                
                <div class="d-flex mx-auto">
                    <v-btn
                        @click="limparCarrinho"
                        text=""
                        class="btn-nav"
                        href="#">
                        Sim
                    </v-btn>
                    <v-btn
                        @click="dialog2 = false"
                        class="ml-4 btn-nav primary"
                        href="#">
                        Não
                    </v-btn>
                </div>
            </v-card>
        </v-dialog>
    </v-container>
</template>

<script>
import CardProduct from './CardProduct'

export default {
    data: () => ({
        dialog: false,
        dialog2: false,
        dialogImg: "",
        dialogText: "",
        img1: "https://contestimg.wish.com/api/webimage/5d530f33538bd178f3ca4ed7-0-feed?cache_buster=f02fe347bf324e1f51a4156b8a50d3df&cozy=1",
        text1: "Carrinho de controle",
        img2: "https://contestimg.wish.com/api/webimage/5d1b3b26136dca0a8f73ec28-0-feed?cache_buster=b9897f1238cd4b23afa9179872bbc87c&cozy=1",
        text2: "Pendriver Kingstion",
        img3: "https://contestimg.wish.com/api/webimage/5d5a37de1e1d981d24fe02b0-0-feed?cache_buster=2a24fbacbc06b5f29572fd41b2403442&cozy=1",
        text3: "Relógio Dourado",
        img4: "https://contestimg.wish.com/api/webimage/5d7b96ca9c40b0162a9dbac7-0-feed?cache_buster=fde871fa667a348b1bc184e75057ce7f&cozy=1",
        text4: "Celular P30 32GB",
        img5: "https://contestimg.wish.com/api/webimage/5d71a5109c80e72d17d04090-0-feed?cache_buster=b4351e890183c9c686e50051da7eac1a&cozy=1",
        text5: "Smartwatch Niband",
        items: ["1GB", "2GB", "8GB", "16GB", "32GB", "64GB"],
        carrinho: [],
        carrinhoItens: 0,
        minimizeCarrinho: false
    }),
    components: {
        CardProduct
    },
    methods: {
        activeDialogLocal(img, text) {
            this.dialog = true
            this.dialogImg = img
            this.dialogText = text
        },
        addToCarrinho(img, text) {
            this.carrinho.push({
                img,
                text
            })
            this.dialog = false
            this.carrinhoItens+=1
        },
        limparCarrinho() {
            this.dialog2 = false
            this.carrinho = []
            this.carrinhoItens = 0
        },
        routeTo(route) {
            this.$router.push(route);
        }
    }
};
</script>

<style lang="scss">
.v-dialog {
    .login-box {
        padding: 10px 30px 30px;
        display: flex;
        align-items: center;
        flex-direction: column;
    }
    .v-tab {
        text-transform: initial;
        font-weight: bold;
        color: rgb(25, 42, 50);
    }

    .content {
        background: white;

        .custom-padding {
            padding: 0 20px;
        }

        .boxDialog {
            margin: 40px 30px 0 0; 
            padding: 32px;
            border-width: 1px;
            border-style: solid;
            border-color: rgb(240, 245, 247);

            h2 {
                font-size: 28px;
                
                span {
                    color: rgb(175, 199, 209);
                    font-weight: normal;
                }
            }

            
        }

        hr {
            border: 3px solid rgb(240, 245, 247);
            padding: 0 16px;
        }
    }

    .btn-nav {
        text-transform: initial;
        font-weight: 400;

        &.primary {
            background: rgb(47, 183, 236);
        }
    }

    .bigimg {
        width: 100%;
        height: 50vh;
        object-fit: cover;
        object-position: center;
    }

    
}

.carrinho {
    position: fixed;
    right: 0;
    top: 112px;
    width: 250px;
    background: white;
    border-left: 1px solid rgb(240, 245, 247);
    height: calc(100% - 112px);
    display: flex;
    flex-direction: column;
    transition: all 0.15s ease;

    &.minimize {
        transform: translateX(200px);
        height: 30px;
        overflow: hidden;
    }

    .headercarrinho {
        display: flex;
        align-items: center;
        justify-content: space-between;

        p {
            color: rgb(47, 183, 236);
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 0;
        }
    }

    &__item {
        display: flex;
        align-items: center;
        border-top: 1px solid rgb(240, 245, 247);   
        padding: 15px ;

        &:last-child {
        border-bottom: 1px solid rgb(240, 245, 247);
    }

        img {
            width: 35%;
            object-fit: contain;
        }

        p {
            margin-bottom: 0px !important;
            margin-left: 5px;
            font-size: 12px;
        }
    }
}
</style>