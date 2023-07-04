<template>
    <n-card class="summary-info" :style="`--labels-color:${labels.backgroundColor}`">
        <template #header>
            <div class="summary-info-header" :style="{ backgroundColor: labels.backgroundColor }">
                <span style="vertical-align: middle;">{{ labels.value }}</span>
            </div>
        </template>
        <template #header-extra>
            <div class="summary-info-icon" :style="{ backgroundColor: labels.backgroundColor }">
                <n-icon style="vertical-align: middle;" color="white" size="25" :component="ArrowCircleUpFilled" />
            </div>
        </template>
        <template #default>
            <div class="summary-info-content" v-for="item, idx in labels.index">
                <span style="font-family: HanSansCN-Bold;">{{ item }}</span><span>{{ labels.content[idx] }}</span>
            </div>
        </template>
    </n-card>
</template>

<script setup lang="ts">
    import { reactive, onMounted } from "vue";
    // import { useI18n } from "vue-i18n";
    import { useSummary } from "@/store";
    import { summaryInfo } from "@/types/summary";
    import { ArrowCircleUpFilled } from "@vicons/material";

    // const { t } = useI18n();
    const summary = useSummary();
    const props = defineProps({ type: String });
    const labels = reactive<summaryInfo>({ name: '', value: '', color: '', backgroundColor: '', index: [''], content: [''], extraLink: null, focused: false });

    const doType = () => {
        switch (props.type) {
            case 'info':
                labels.value = summary.info.value;
                labels.backgroundColor = summary.info.color;
                labels.color = "white";
                labels.index = summary.info.index;
                labels.content = summary.info.content;
                labels.focused = summary.info.focused;
                break;
            case 'classification':
                labels.value = summary.classify.value;
                labels.backgroundColor = summary.classify.color;
                labels.color = "white";
                labels.index = summary.classify.index;
                labels.content = summary.classify.content;
                labels.focused = summary.classify.focused;
                break;
            case 'clinvar':
                labels.value = summary.clinvar.value;
                labels.backgroundColor = summary.clinvar.color;
                labels.color = "white";
                labels.index = summary.clinvar.index;
                labels.content = summary.clinvar.content;
                labels.focused = summary.clinvar.focused;
                break;
            case 'omim':
                labels.value = summary.omim.value;
                labels.backgroundColor = summary.omim.color;
                labels.color = "white";
                labels.index = summary.omim.index;
                labels.content = summary.omim.content;
                labels.focused = summary.omim.focused;
                break;
            case 'gnomAD':
                labels.value = summary.gnomAD.value;
                labels.backgroundColor = summary.gnomAD.color;
                labels.color = "white";
                labels.index = summary.gnomAD.index;
                labels.content = summary.gnomAD.content;
                labels.focused = summary.gnomAD.focused;
                break;
            case 'swp':
                labels.value = summary.swp.value;
                labels.backgroundColor = summary.swp.color;
                labels.color = "white";
                labels.index = summary.swp.index;
                labels.content = summary.swp.content;
                labels.focused = summary.swp.focused;
                break;
        }
    }

    onMounted(() => {
        doType();
    })
</script>

<style lang="css">
    .n-card {
        margin-top: 20px;
        width: 400px;
        height: 130px;
        margin-right: 5px;
    }
    .n-card > .n-card-header {
        padding: 0;    
    }
    .n-card > .n-card__content {
        padding: 0;
    }
    .n-card.n-card--bordered {
        border-top-left-radius: 7px;
        border-top-right-radius: 7px;
        border: 1px solid var(--labels-color);
    }
    .summary-info {
        cursor: pointer;
        border-top-left-radius: 5px;
        border-top-right-radius: 5px;
    }
    .summary-info:hover {
        border-top-left-radius: 7px;
        border-top-right-radius: 7px;
        box-shadow: 0 0 10px var(--labels-color);
    }
    .summary-info-header {
        height: 30px;
        border-top-left-radius: 5px;
        font-family: HanSansCN-Bold;
        text-align: left;
        color: white;
        padding-left: 12px;
        font-size: 16px;
    }
    .summary-info-icon {
        height: 30px;
        border-top-right-radius: 5px;
    }
    .summary-info-content {
        text-align: left; 
        padding-left: 12px;
        font-size: 12px;
        line-height: 22px;
    }
</style>