<template>
    <v-container>
        <v-row style="max-width: 1200px; margin: auto">
            <v-col cols="12" sm="12" md="8" lg="8">
                <div class="headertable">
                    Itens Adicionados ao Carrinho
                </div>
                <div class="headerbody">
                    <div class="productItem" v-if="text1">
                        <v-row>
                            <v-col cols=12 sm=12 md=3 lg=3 class="left">
                                <img :src="img1" alt="">
                            </v-col>
                            <v-col cols=12 sm=12 md=9 lg=9 class="right d-flex flex-column">
                                <div class="d-flex">
                                    <p style="font-weight: bold; font-size: 18px;" class="pr-4">{{text1}}</p>
                                    <p style="min-width: 100px;" class="mr-4">{{preco1}}</p>
                                </div>
                                <div class="d-flex">
                                    <p class="pr-4">Entrega Expressa Chegando até a próxima Segunda-Feira:</p>
                                    <p style="min-width: 100px;" class="mr-4">R$41,87 BRL</p>
                                </div>
                                <v-btn
                                    @click="text1 = false"
                                    class="ml-auto mr-4"
                                    depressed
                                    style="text-transform: initial"
                                    color="warning">
                                    Remover
                                </v-btn>
                            </v-col>
                        </v-row>
                    </div>
                    <div class="productItem" v-if="text2">
                        <v-row>
                            <v-col cols=12 sm=12 md=3 lg=3 class="left">
                                <img :src="img2" alt="">
                            </v-col>
                            <v-col cols=12 sm=12 md=9 lg=9 class="right d-flex flex-column">
                                <div class="d-flex">
                                    <p style="font-weight: bold; font-size: 18px;" class="pr-4">{{text2}}</p>
                                    <p style="min-width: 100px;" class="mr-4">{{preco2}}</p>
                                </div>
                                <div class="d-flex">
                                    <p class="pr-4">Entrega Expressa Chegando até a próxima Segunda-Feira:</p>
                                    <p style="min-width: 100px;" class="mr-4">R$41,87 BRL</p>
                                </div>
                                <v-btn
                                    @click="text2 = false"
                                    class="ml-auto mr-4"
                                    depressed
                                    style="text-transform: initial"
                                    color="warning">
                                    Remover
                                </v-btn>
                            </v-col>
                        </v-row>
                    </div>
                    <div class="productItem" v-if="text3">
                        <v-row>
                            <v-col cols=12 sm=12 md=3 lg=3 class="left">
                                <img :src="img3" alt="">
                            </v-col>
                            <v-col cols=12 sm=12 md=9 lg=9 class="right d-flex flex-column">
                                <div class="d-flex">
                                    <p style="font-weight: bold; font-size: 18px;" class="pr-4">{{text3}}</p>
                                    <p style="min-width: 100px;" class="mr-4">{{preco3}}</p>
                                </div>
                                <div class="d-flex">
                                    <p class="pr-4">Entrega Expressa Chegando até a próxima Segunda-Feira:</p>
                                    <p style="min-width: 100px;" class="mr-4">R$41,87 BRL</p>
                                </div>
                                <v-btn
                                    @click="text3 = false"
                                    class="ml-auto mr-4"
                                    depressed
                                    style="text-transform: initial"
                                    color="warning">
                                    Remover
                                </v-btn>
                            </v-col>
                        </v-row>
                    </div>
                </div>
            </v-col>
            <v-col cols="12" sm="12" md="4" lg="4">
                <div class="headertable">
                    Resumo do pedido
                </div>
                <div class="headerbody pa-4">
                    <ul style="list-style: none" class="pl-0">
                        <li>
                            <div class="d-flex">
                                <p class="mb-0">
                                    Subtotal:
                                </p>
                                <p class="ml-auto mb-0">
                                    R$113,00 BRL
                                </p>
                            </div>
                        </li>
                        <li>
                            <div class="d-flex">
                                <p class="mb-0">
                                    Frete:
                                </p>
                                <p class="ml-auto mb-0">
                                    R$125,49 BRL
                                </p>
                            </div>
                        </li>
                        <li>
                            <div class="d-flex">
                                <p class="mb-0">
                                    Total:
                                </p>
                                <p class="ml-auto mb-0" style="font-weight: bold">
                                    R$238,49 BRL
                                </p>
                            </div>
                        </li>
                    </ul>
                    <div class="headerbodyfooter mt-3 pt-3">
                        <v-btn
                            @click="dialog2 = true"
                            style="text-transform: initial"
                            block
                            color="success"
                            depressed>
                            Finalizar
                        </v-btn>
                    </div>
                </div>
            </v-col>
        </v-row>
        
        <v-dialog v-model="dialog2" max-width="500" >
            <v-card class="login-box">
                <div class="d-flex align-center" style="width: 100%;">
                    <v-card-title class="title px-0">Você precisa estar logado para continuar!</v-card-title>
                    
                    <v-btn
                        icon=""
                        class="ml-auto"
                        @click="dialog2 = false">
                        <v-icon>mdi-close</v-icon>
                    </v-btn>
                </div>

                <p>Faça o login ou cadastre-se para poder finalizar a compra.</p>
                
                <div class="d-flex mx-auto">
                    <v-btn
                        @click="dialog2 = false"
                        text=""
                        class="btn-nav"
                        href="#">
                        Logar
                    </v-btn>
                    <v-btn
                        @click="dialog2 = false"
                        class="ml-4 btn-nav primary"
                        href="#">
                        Cadastrar
                    </v-btn>
                </div>
            </v-card>
        </v-dialog>
    </v-container>
</template>

<script>

export default {
    data: () => ({
        dialog: false,
        dialog2: false,
        dialogImg: "",
        dialogText: "",
        img1: "https://contestimg.wish.com/api/webimage/5d530f33538bd178f3ca4ed7-0-feed?cache_buster=f02fe347bf324e1f51a4156b8a50d3df&cozy=1",
        text1: "Carrinho de controle vermelho - 20mts de alcance para as crianças",
        preco1: "R$50,00 BRL",
        img2: "https://contestimg.wish.com/api/webimage/5d1b3b26136dca0a8f73ec28-0-feed?cache_buster=b9897f1238cd4b23afa9179872bbc87c&cozy=1",
        text2: "Pendriver Kingstion - 32GB removível a prova dágua",
        preco3: "R$48,00 BRL",
        img3: "https://contestimg.wish.com/api/webimage/5d5a37de1e1d981d24fe02b0-0-feed?cache_buster=2a24fbacbc06b5f29572fd41b2403442&cozy=1",
        text3: "Relógio Dourado WaterProof Mans - Cronômetro, despertador, analógico",
    }),
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
.v-content__wrap {
    background: white !important;

    .headertable {
        border: 1px solid rgb(212, 227, 235);
        font-size: 16px;
        padding: 10px 20px;
        font-weight: bold;
        background: rgb(240, 245, 247);
    }

    .headerbody {
        border: 1px solid rgb(212, 227, 235);

        .productItem {
            border-bottom: 1px solid rgb(212, 227, 235);
            padding: 10px 0;
        }
        .left {
            display: flex;
            align-items: center;
            justify-content: center;
            img {
                width: 80%;
            }
        }
        .headerbodyfooter {
            border-top: 1px solid rgb(212, 227, 235);
        }
    }
}
</style>