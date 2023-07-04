<template>
    <div style="padding: 30px 0 10px 15px;text-align: left;font-size: 20px;margin-top: 10px;">
        <a style="padding: 0 20px;" href="" target="_blank">PMID164660646</a>, <a href="" target="_blank">PMC3525152</a> <br /><br />
        <div style="font-size: 20px;;padding: 0 20px;font-family: HanSansCN-Bold;">{{ t('paper.line1') }}</div><br />
        <n-scrollbar trigger="hover" :style="{ maxHeight: props.size }">
            <template #default>
                <div style="font-size: 18px;word-wrap: break-word;padding: 0 20px;">
                    {{ t('paper.line2') }}<br /><br />{{ t('paper.line3') }}<br /><br />{{ t('paper.line4') }}
                    {{ t('paper.line2') }}<br /><br />{{ t('paper.line3') }}<br /><br />{{ t('paper.line4') }}
                    {{ t('paper.line2') }}<br /><br />{{ t('paper.line3') }}<br /><br />{{ t('paper.line4') }}
                    {{ t('paper.line2') }}<br /><br />{{ t('paper.line3') }}<br /><br />{{ t('paper.line4') }}
                    {{ t('paper.line2') }}<br /><br />{{ t('paper.line3') }}<br /><br />{{ t('paper.line4') }}
                    {{ t('paper.line2') }}<br /><br />{{ t('paper.line3') }}<br /><br />{{ t('paper.line4') }}
                    {{ t('paper.line2') }}<br /><br />{{ t('paper.line3') }}<br /><br />{{ t('paper.line4') }}
                    {{ t('paper.line2') }}<br /><br />{{ t('paper.line3') }}<br /><br />{{ t('paper.line4') }}
                </div>
            </template>
        </n-scrollbar>

    </div>    
</template>

<script setup lang="ts">
    import { useI18n } from "vue-i18n";

    const props = defineProps(['size']);

    const { t } = useI18n();
</script>