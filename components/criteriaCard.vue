<template>
    <div class="card-size" :style="{ backgroundColor:criteria.color, borderColor:criteria.color }">
        <div style="display: flex;line-height: 10px;color: white;">
            <div style="flex: 4;font-family: HanSansCN-Bold;font-size: 14px;margin-top: 2px;">{{ criteria.name }}</div>
            <div style="flex: 2;margin-top: -1px;">
                <n-popover trigger="hover">
                    <template #trigger>
                        <n-icon class="pointer" size="16" :component="QuestionCircle32Regular" />
                    </template>
                    {{ criteria.tips }}
                </n-popover>
            </div>
        </div>
        <div style="line-height: 18px;color: white;">{{ criteria.strength }}</div>
    </div>
</template>

<script setup lang="ts">
    import { onMounted,reactive } from "vue";
    import { useSummary } from "../../store";
    import { QuestionCircle32Regular } from "@vicons/fluent";

    const summary = useSummary();
    const props = defineProps(['info']);
    const criteria = reactive({ name:'', strength:'', tips:'', color:'' });

    const decision = () => {
        if (typeof(props.info)=='string') {
            switch (props.info) {
                case "PM3":
                    criteria.name = summary.criteriaTest.name;
                    criteria.tips = summary.criteriaTest.tips;
                    criteria.strength = summary.criteriaTest.strengh;
                    criteria.color = summary.criteriaTest.color;
                    break;
                case "PP1":
                    criteria.name = summary.criteriaTest1.name;
                    criteria.tips = summary.criteriaTest1.tips;
                    criteria.strength = summary.criteriaTest1.strengh;
                    criteria.color = summary.criteriaTest1.color;
                    break;
                case "BS3":
                    criteria.name = summary.criteriaTest2.name;
                    criteria.tips = summary.criteriaTest2.tips;
                    criteria.strength = summary.criteriaTest2.strengh;
                    criteria.color = summary.criteriaTest2.color;
                    break;
                case "PM2":
                    criteria.name = summary.criteriaTest3.name;
                    criteria.tips = summary.criteriaTest3.tips;
                    criteria.strength = summary.criteriaTest3.strengh;
                    criteria.color = summary.criteriaTest3.color;
                    break;
                case "BS1":
                    criteria.name = summary.criteriaTest4.name;
                    criteria.tips = summary.criteriaTest4.tips;
                    criteria.strength = summary.criteriaTest4.strengh;
                    criteria.color = summary.criteriaTest4.color;
                    break;
                case "BA1":
                    criteria.name = summary.criteriaTest5.name;
                    criteria.tips = summary.criteriaTest5.tips;
                    criteria.strength = summary.criteriaTest5.strengh;
                    criteria.color = summary.criteriaTest5.color;
                    break;
                case "BS2":
                    criteria.name = summary.criteriaTest6.name;
                    criteria.tips = summary.criteriaTest6.tips;
                    criteria.strength = summary.criteriaTest6.strengh;
                    criteria.color = summary.criteriaTest6.color;
                    break;
                case "PVS1":
                    criteria.name = summary.criteriaTest7.name;
                    criteria.tips = summary.criteriaTest7.tips;
                    criteria.strength = summary.criteriaTest7.strengh;
                    criteria.color = summary.criteriaTest7.color;
                    break;
                case "PM1":
                    criteria.name = summary.criteriaTest8.name;
                    criteria.tips = summary.criteriaTest8.tips;
                    criteria.strength = summary.criteriaTest8.strengh;
                    criteria.color = summary.criteriaTest8.color;
                    break;
                case "PP3":
                    criteria.name = summary.criteriaTest9.name;
                    criteria.tips = summary.criteriaTest9.tips;
                    criteria.strength = summary.criteriaTest9.strengh;
                    criteria.color = summary.criteriaTest9.color;
                    break;
                case "BP4":
                    criteria.name = summary.criteriaTest10.name;
                    criteria.tips = summary.criteriaTest10.tips;
                    criteria.strength = summary.criteriaTest10.strengh;
                    criteria.color = summary.criteriaTest10.color;
                    break;
                case "PM4":
                    criteria.name = summary.criteriaTest11.name;
                    criteria.tips = summary.criteriaTest11.tips;
                    criteria.strength = summary.criteriaTest11.strengh;
                    criteria.color = summary.criteriaTest11.color;
                    break;
                case "BP3":
                    criteria.name = summary.criteriaTest12.name;
                    criteria.tips = summary.criteriaTest12.tips;
                    criteria.strength = summary.criteriaTest12.strengh;
                    criteria.color = summary.criteriaTest12.color;
                    break;
                case "BP7":
                    criteria.name = summary.criteriaTest13.name;
                    criteria.tips = summary.criteriaTest13.tips;
                    criteria.strength = summary.criteriaTest13.strengh;
                    criteria.color = summary.criteriaTest13.color;
                    break;
                case "PS1":
                    criteria.name = summary.criteriaTest14.name;
                    criteria.tips = summary.criteriaTest14.tips;
                    criteria.strength = summary.criteriaTest14.strengh;
                    criteria.color = summary.criteriaTest14.color;
                    break;
                case "PM5":
                    criteria.name = summary.criteriaTest15.name;
                    criteria.tips = summary.criteriaTest15.tips;
                    criteria.strength = summary.criteriaTest15.strengh;
                    criteria.color = summary.criteriaTest15.color;
                    break;
                case "BP2":
                    criteria.name = summary.criteriaTest16.name;
                    criteria.tips = summary.criteriaTest16.tips;
                    criteria.strength = summary.criteriaTest16.strengh;
                    criteria.color = summary.criteriaTest16.color;
                    break;
                case "PS2":
                    criteria.name = summary.criteriaTest17.name;
                    criteria.tips = summary.criteriaTest17.tips;
                    criteria.strength = summary.criteriaTest17.strengh;
                    criteria.color = summary.criteriaTest17.color;
                    break;
                case "PM6":
                    criteria.name = summary.criteriaTest18.name;
                    criteria.tips = summary.criteriaTest18.tips;
                    criteria.strength = summary.criteriaTest18.strengh;
                    criteria.color = summary.criteriaTest18.color;
                    break;
                case "PP4":
                    criteria.name = summary.criteriaTest19.name;
                    criteria.tips = summary.criteriaTest19.tips;
                    criteria.strength = summary.criteriaTest19.strengh;
                    criteria.color = summary.criteriaTest19.color;
                    break;
                case "BP5":
                    criteria.name = summary.criteriaTest20.name;
                    criteria.tips = summary.criteriaTest20.tips;
                    criteria.strength = summary.criteriaTest20.strengh;
                    criteria.color = summary.criteriaTest20.color;
                    break;
                case "PP1":
                    criteria.name = summary.criteriaTest21.name;
                    criteria.tips = summary.criteriaTest21.tips;
                    criteria.strength = summary.criteriaTest21.strengh;
                    criteria.color = summary.criteriaTest21.color;
                    break;
                case "BS4":
                    criteria.name = summary.criteriaTest22.name;
                    criteria.tips = summary.criteriaTest22.tips;
                    criteria.strength = summary.criteriaTest22.strengh;
                    criteria.color = summary.criteriaTest22.color;
                    break;
                case "PS4":
                    criteria.name = summary.criteriaTest23.name;
                    criteria.tips = summary.criteriaTest23.tips;
                    criteria.strength = summary.criteriaTest23.strengh;
                    criteria.color = summary.criteriaTest23.color;
                    break;
                case "PS3":
                    criteria.name = summary.criteriaTest24.name;
                    criteria.tips = summary.criteriaTest24.tips;
                    criteria.strength = summary.criteriaTest24.strengh;
                    criteria.color = summary.criteriaTest24.color;
                    break;
            }
        }else if(typeof(props.info)=='object'){
            switch (props.info) {
                case "PM3":
                    criteria.name = summary.criteriaTest.name;
                    criteria.tips = summary.criteriaTest.tips;
                    criteria.strength = summary.criteriaTest.strengh;
                    criteria.color = summary.criteriaTest.color;
                    break;
                case "PP1":
                    criteria.name = summary.criteriaTest1.name;
                    criteria.tips = summary.criteriaTest1.tips;
                    criteria.strength = summary.criteriaTest1.strengh;
                    criteria.color = summary.criteriaTest1.color;
                    break;
                case "BS3":
                    criteria.name = summary.criteriaTest2.name;
                    criteria.tips = summary.criteriaTest2.tips;
                    criteria.strength = summary.criteriaTest2.strengh;
                    criteria.color = summary.criteriaTest2.color;
                    break;
            }
        }
    }

    onMounted(() => {
        decision();
    })

</script>

<style lang="css">
    .pointer {
        cursor: pointer;
    }
    .card-size {
        width: 80px;
        height: 40px;
        font-size: 12px;
        border-radius: 5px;
        border: 1px solid;
        display: flex;
        justify-content: space-evenly;
        flex-direction: column;
        margin-left: 10px;
    }
    .n-icon:hover {
        color: white;
    }
</style>