<template>
    <div class="card-item">
        <img :src="img" alt="">
        <div>
            <p class="mb-1">{{value}}<small class="risked"> {{nonvalue}}</small></p>
            <p class="gray">1000+ compraram esse produto</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        img : {
            type: String
        },
        value: {
            type: String
        },
        nonvalue: {
            type: String
        },
    }
}
</script>

<style lang="scss">
.card-item {
    width: 100%;
    height: 280px;
    display: flex;
    flex-direction: column;
    background: white;
    box-shadow: rgba(0, 0, 0, 0.05) 0px 0px 0px 0px, rgba(0, 0, 0, 0.05) 0px 2px 20px 0px;
    transition: all 0.3s ease;

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
            color: rgb(126, 154, 166);
            font-size: 12px;
        }

        small {
            padding-left: 10px;
            text-decoration: line-through;
            color: rgb(126, 154, 166);
        }
    }


}
</style>