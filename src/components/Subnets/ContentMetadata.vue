<template>
    <div class="metadata">
        <div>
            <div class="meta_data">
                <div>
                    <div>
                        <p class="label">
                            Blockchains
                            <TooltipMeta
                                content="Total number of blockchains created on this subnetwork"
                            ></TooltipMeta>
                        </p>
                        <p class="meta_val">{{ totalBlockchains }}</p>
                    </div>
                </div>
                <div>
                    <div>
                        <p class="label">
                            Validators
                            <TooltipMeta
                                content="Total number of nodes participating in the consensus protocol of this subnetwork"
                            ></TooltipMeta>
                        </p>
                        <p class="meta_val">{{ totalValidators }}</p>
                    </div>
                </div>
                <div>
                    <div>
                        <p class="label">
                            Pending Validators
                            <TooltipMeta
                                content="Total number of nodes waiting to participate in the consensus protocol of this subnetwork"
                            ></TooltipMeta>
                        </p>
                        <p class="meta_val">{{ totalPendingValidators }}</p>
                    </div>
                </div>
                <div>
                    <div>
                        <p class="label">
                            Control Keys
                            <TooltipMeta
                                content="In order to add a validator to a subnet, threshold signatures from keys are needed"
                            ></TooltipMeta>
                        </p>
                        <p class="meta_val">{{ totalControlKeys }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import Big from 'big.js'
import TooltipMeta from '../../components/misc/TooltipMeta'

export default {
    components: {
        TooltipMeta,
    },
    props: {
        totalBlockchains: Number,
        totalValidators: Number,
        totalPendingValidators: Number,
        totalControlKeys: Number,
    },
}
</script>
<style scoped lang="scss">
.metadata {
    margin-bottom: 15px;
    .header {
        display: flex;
        justify-content: space-between;
    }
}

.meta_data {
    display: grid;
    width: 100%;
    grid-template-columns: 25% 25% 25% 25%;

    > div {
        padding: 30px 15px;
        text-align: left;
        line-height: 1.4em;
        display: flex;
        flex-direction: row;
        align-items: center;
        flex-wrap: wrap;
    }

    p {
        font-weight: 400; /* 700 */
    }

    .label {
        text-transform: capitalize;
        font-size: 12px;
        font-weight: 700;
        margin-bottom: 6px;
        color: $primary-color;
    }

    .meta_val {
        font-size: 36px;
        line-height: 1em;
        font-weight: 300;
        color: $primary-color;
    }
}

@include smOnly {
    .meta_data {
        grid-template-columns: 50% 50%;

        img {
            display: none;
        }

        > div {
            padding: 30px 0 0;
        }

        .meta_val {
            font-size: 20px;
        }
    }
}
</style>
