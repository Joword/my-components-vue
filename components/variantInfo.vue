<template>
    <n-data-table :bordered="false" :columns="columns" :data="data"/>
</template>

<script setup lang="ts">
    import { h, reactive } from "vue";
    import { VariantRows } from "@/types/info";
    import { NText, DataTableColumns } from "naive-ui";

    const columns:DataTableColumns<VariantRows> =  reactive<DataTableColumns<VariantRows>>([
        {
            title: (():any => {
                        return h(
                            NText,
                            { style: { fontFamily: 'HanSansCN-Bold', fontSize: '18px' } },
                            { default: () => "Variants" }
                        )
                    }),
            key: 'variant',
            ellipsis: {
                tooltip: true
            }
        },
        {
            title: (():any => {
                        return h(
                            NText,
                            { style: { fontFamily: 'HanSansCN-Bold', fontSize: '18px' } },
                            { default: () => "cHGVS" }
                        )
                    }),
            key: 'chgvs'
        },
        {
            title: (():any => {
                        return h(
                            NText,
                            { style: { fontFamily: 'HanSansCN-Bold', fontSize: '18px' } },
                            { default: () => "pHGVS" }
                        )
                    }),
            key: 'phgvs'
        },
        {
            title:(():any => {
                        return h(
                            NText,
                            { style: { fontFamily: 'HanSansCN-Bold', fontSize: '18px' } },
                            { default: () => "Consequence" }
                        )
                    }),
            key: 'consequence',
        },
        {
            title:(():any => {
                        return h(
                            NText,
                            { style: { fontFamily: 'HanSansCN-Bold', fontSize: '18px' } },
                            { default: () => "Criteria" }
                        )
                    }),
            key: 'criteria',
        },
        {
            title:(():any => {
                        return h(
                            NText,
                            { style: { fontFamily: 'HanSansCN-Bold', fontSize: '18px' } },
                            { default: () => "Classification" }
                        )
                    }),
            key: 'classification',
        },
    ]);

    const data:VariantRows[] = [
        {
            key: 0,
            variant: '7-107301238-C-G',
            chgvs: '-',
            phgvs: '-',
            consequence: 'upstream_gene',
            criteria: 'BA1,BS2',
            classification: 'Benign'
        },
        {
            key: 1,
            variant: '7-107302101-C-A',
            chgvs: 'NM_000441.2:c.15C>A',
            phgvs: 'NP_000432.1:p.Gly5=',
            consequence: 'synonymous',
            criteria: 'BA1,BS2,BP4,BP7',
            classification: 'Benign'
        },
        {
            key: 2,
            variant: '7-107302103-G-T',
            chgvs: 'NM_000441.2:c.17G>T',
            phgvs: 'NP_000432.1:p.Gly6Val',
            consequence: 'missense',
            criteria: 'BA1,BS2',
            classification: 'Benign'
        },
        {
            key: 3,
            variant: '7-107303628-C-T',
            chgvs: 'NM_000441.2:c.165-113C>T',
            phgvs: '-',
            consequence: 'intron',
            criteria: 'BA1,BS2,BP4',
            classification: 'Benign'
        },
        {
            key: 4,
            variant: '7-107314602-T-C',
            chgvs: 'NM_000441.2:c.416-7T>C',
            phgvs: '-',
            consequence: 'splice_region,intron',
            criteria: 'BA1,BP4',
            classification: 'Benign'
        }
    ];
</script>

<style scoped>

</style>