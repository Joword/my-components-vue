<template>
    <n-row class="chat-text">
        <n-col :span="24">
            <n-row style="margin: 10px 10px 0 0;height: 30px;">
                <n-col style="width: 20px;"></n-col>
                <n-col :span="1" class="chatpaper-logo">
                    <n-icon size="20" :component="Bot20Filled" />
                </n-col>
                <n-col :span="21" class="chatpaper-title">
                    {{ t('modules.chat') }}
                    <n-icon @click="chatEvent('close')" size="20" class="icon-style-pointer" id="close" :component="Close" />
                    <n-icon @click="chatEvent('update')" size="20" class="icon-style-pointer" id="refresh" :component="Refresh" />
                </n-col>
                <n-col style="width: 20px;"></n-col>
            </n-row>
            <n-scrollbar style="max-height: 650px;padding-bottom: 5px;">
                <AnswerCard :info="'bot.welcome'"></AnswerCard>
                <QuestionCard :info="'bot.question1'"></QuestionCard>
                <AnswerCard :info="'bot.answer1'"></AnswerCard>
                <QuestionCard :info="'bot.question2'"></QuestionCard>
                <AnswerCard :info="'bot.answer2'"></AnswerCard>
            </n-scrollbar>
            <n-row style="height: 40px;">
                <n-input v-model:value="chatTextInput" class="chatbgi-input" placeholder="" clearable>
                    <template #prefix>
                        <n-icon class="icon-edit" :component="Edit" />
                    </template>
                    <template #suffix>
                        <n-icon class="pointer" :component="Send" />
                    </template>
                </n-input>
            </n-row>
        </n-col>
    </n-row>
</template>

<script setup lang="ts">
    import { ref } from "vue";
    import { useI18n } from "vue-i18n";
    // import { Conversation } from "@/types/chatpaper";
    import { informations } from "../../store";

    import { Send } from "@vicons/tabler";
    import { Edit } from "@vicons/carbon";
    import { Bot20Filled } from "@vicons/fluent";
    import { Refresh, Close } from "@vicons/ionicons5";

    import AnswerCard from "./answercard.vue";
    import QuestionCard from "./questioncard.vue";
    

    const { t } = useI18n();
    const chatTextInput = ref('');
    const msg = informations();
    // const answer = ref<Conversation>();
    // const question = ref<Conversation>();

    const chatEvent = (arg:string) => {
        switch (arg) {
            case "close":
                msg.chatpaper.value = false;
                msg.chatpaper.color = "#F5F5F5"
                break;
            case "update":

                break;
        }
    }

</script>

<style lang="css">
    #close:hover {
        color: grey;
    }
    #refresh:hover {
        color:grey;
    }

    .chat-text {
        min-height: 750px;
        border: 0.15rem solid #A6A6A6;
        border-radius: 5px;
        width: 100%;
    }
    .pointer {
        cursor: pointer;
    }
    .icon-style-pointer {
        cursor: pointer;
        vertical-align: sub;
        float: right;
    }
    .icon-edit:hover {
        color:#18a058;
    }
    .chatbgi-input {
        margin: 0 10px;
        text-align: left;
        border: 1px grey;
        border-radius: 8px;
    }
    .chatpaper-logo {
        min-width: 25px;
        vertical-align: middle;
    }
    .chatpaper-button-group {
        width: 650px;
    }
    .chatpaper-title {
        text-align: left;
        font-family: HanSansCN-Bold;
        padding-left: 10px;
        min-width: 50px;margin-bottom: 10px;
    }
</style>