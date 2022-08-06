<template>
    <div><input v-model="msg" type="text" /></div>
    <div v-for="item in names" :key="item">{{ item }}</div>
    <ul>
        <li v-for="item in memberList" :key="item.id">{{ item.name }}</li>
    </ul>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted, reactive } from 'vue';

// person interface
interface Member {
    id: number,
    name: string,
}

export default defineComponent({
    setup() {
        const msg = ref<string>('Hello, world!');
        const uids = ref<number[]>([1, 2, 3]);
        const names = ref<string[]>(['Tom', 'Jerry', 'Andy']);
        const memberList = ref<Member[]>([
            { id: 1, name: 'Tom' },
            { id: 2, name: 'Jerry' },
            { id: 3, name: 'Dida' }
        ]);
        const userInfo: Member = reactive({
            id: 1,
            name: 'Tom'
        });

        setTimeout(()=>{
            msg.value = 'Opsss...'
        }, 1000);

        onMounted(() => {
            console.log('onMounted');
            console.log(msg.value);
            console.log(uids.value[1]);
            console.log(userInfo.name);
        });
        return {
            msg,
            names,
            memberList,
            uids,
        }
    },

}
);

</script>

<style scoped>
.msg {
    font-size: 14px;
}
</style>