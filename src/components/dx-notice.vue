<template>
    <div id="dx-notice" w-100>
        <m-button>开发公告</m-button>
        <m-table :data="todoList" h-full>
            <m-table-column width="80px" param="id" label="序号" />
            <m-table-column param="todo" label="功能" />
            <m-table-column param="todo" label="状态">
                <template #default="{data}">
                    <div flex="~ row none" justify-center items-center>
                        <m-tag type="primary" v-if="data.state">已完成</m-tag>
                        <m-tag v-else>进行中</m-tag>
                    </div>
                </template>

            </m-table-column>
        </m-table>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const todoList = ref([
    { id: 1, todo: '基本功能', state: 1 },
    { id: 2, todo: '公告看板', state: 1 },
    { id: 3, todo: '竹笛音源录制', state: 1 },
    { id: 4, todo: '移动端适配', state: 1 },
    { id: 5, todo: '网站icon', state: 1 },
    { id: 6, todo: '自动演奏', state: 0 },
    { id: 7, todo: 'websocket', state: 0 },

]);

</script>

<style scoped lang='less'>
#dx-notice {
    position: fixed;
    top: 50%;
    left: 5ch;
    display: flex;
    flex-direction: column;
    gap: 16px;
    transform: translateY(-50%);
    justify-content: center;
    align-items: center;

    &::-webkit-scrollbar {
        display: none;
        /* Chrome Safari */

    }
}
</style>