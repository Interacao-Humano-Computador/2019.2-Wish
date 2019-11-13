<template>
    <div class="card-item" @click="activeDialog">
        <img :src="img" alt="">
        <div>
            <p class="mb-1 mt-2">{{description}}</p>
            <p class="mb-1 gray">{{value}}<small class="risked"> {{nonvalue}}</small></p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        description : {
            type: String
        },
        img : {
            type: String
        },
        value: {
            type: String
        },
        nonvalue: {
            type: String
        },
    },
    methods: {
        activeDialog() {
            this.$emit('activeDialog')
        }
    }
}
</script>

<style lang="scss">
.card-item {
    width: 100%;
    height: 290px;
    display: flex;
    flex-direction: column;
    background: white;
    box-shadow: rgba(0, 0, 0, 0.05) 0px 0px 0px 0px, rgba(0, 0, 0, 0.05) 0px 2px 20px 0px;
    transition: all 0.3s ease;
    cursor: pointer;

    &:hover {
        transform: scale(1.05);
        z-index: 1;
        overflow: visible;
    }

    img {
        width: 100%;
        height: 220px;
        object-fit: cover;
    }

    p {
        margin: 0 10px;
        color: black;

        &.gray {
            font-size: 14px;
        }

        small {
            padding-left: 10px;
            font-size: 13px;
            text-decoration: line-through;
            color: rgb(126, 154, 166);
        }
    }


}
</style>