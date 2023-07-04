<template>
    <div style="line-height: 50px;display: flex;">
        <span style="flex: 1;min-width: 90px;">{{ t('commons.articleAdd') }}</span>
        <div style="flex: 3;">
            <n-input :placeholder="$t('commons.articleAddPlaceholder')" clearable>
                <template #suffix>
                    <n-icon :component="Add12Filled"></n-icon>
                </template>
            </n-input>
        </div>
        <div style="flex: 12"></div>
        <div style="flex: 4;text-align: left;display: flex;">
            <div style="min-width: 60px;">{{ t('commons.search') }}</div>
            <div style="flex: 3;">
                <n-input placeholder="" clearable></n-input>
            </div>
            <div style="flex: 1"></div>
        </div>
    </div>
    <n-data-table :columns="articleColumns" :data="ariticleData" :bordered="false"/>
</template>

<script setup lang="ts">

    import { h } from 'vue'
    import { useI18n } from "vue-i18n";
    import { DataTableColumns, NSpace, NIcon } from "naive-ui";

    import { Edit } from "@vicons/tabler";
    import { Add12Filled } from "@vicons/fluent";
    import { ArticleTables } from "@/types/summary";
    import { ThumbsUp, ThumbsUpFilled } from "@vicons/carbon";

    import CriteriaCard from "./criteriaCard.vue";

    const { t } = useI18n();

    const ariticleData: ArticleTables[] = [
        
        ];
    const articleColumns: DataTableColumns<ArticleTables> = [
        {
            key: 'article',
            title: (() => {
                return h(
                    NSpace,
                    { style: { fontFamily: 'HanSansCN-Bold', fontSize: '16px' } },
                    { default: () => "Article" }
                )
            }),
            resizable: true,
            width: 170,
            minWidth: 170,
            maxWidth: 200,

        },
        {
            key: 'criteria',
            title: (() => {
                return h(
                    NSpace,
                    { style: { fontFamily: 'HanSansCN-Bold', fontSize: '16px' } },
                    { default: () => "Criteria" }
                )
            }),
            resizable: true,
            width: 120,
            minWidth: 120,
            maxWidth: 180,
            rowSpan: (rowData, rowIndex) => {
                switch (rowIndex) {
                    case 13:
                        return 5;
                        rowData;
                    case 27:
                        return 2;
                    default:
                        return 1;
                }
            },
            render(row){
                return h(
                    CriteriaCard,
                    { info: row.criteria },
                    { default:() => {} }
                )
            },

        },
        {
            key: 'evidence',
            title: (() => {
                return h(
                    NSpace,
                    { style: { fontFamily: 'HanSansCN-Bold', fontSize: '16px' } },
                    { default: () => "Evidence" }
                )
            }),
            resizable: true,
            width: 800,
            minWidth: 800,
            maxWidth: 850,
            ellipsis: {
                tooltip: true
            }

        },
        {
            key: 'comments',
            title: (() => {
                return h(
                    NSpace,
                    { style: { fontFamily: 'HanSansCN-Bold', fontSize: '16px' } },
                    { default: () => "Comments" }
                )
            }),
            resizable: true,
            width: 100,
            render(row){
                return h(
                    'div',
                    null,
                    [h(NIcon,
                        {
                            size: 25,
                            class: ['comment-thumbup'],
                            style: { cursor: 'pointer' },
                            onClick: () => {
                                switch (row.thumbup) {
                                    case 0:
                                        row.thumbup = 1;
                                        break;
                                    case 1:
                                        row.thumbup = 0;
                                        break;
                                }
                            }
                        },
                        { default: () => row.thumbup===1?h(ThumbsUpFilled):h(ThumbsUp) }),
                        h(NIcon,
                        {
                            size: 25,
                            class: ['comment-edit'],
                            style: { cursor: 'pointer', marginLeft:'10px' },
                            onClick: () => {
                                row.thumbup
                            }
                        },
                        { default: () => h(Edit) }
                    )]
                )
            }

        }
    ];
</script>

<style lang="scss">

</style>