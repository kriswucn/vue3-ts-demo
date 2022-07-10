<template>
    <div><input v-model="msg" type="text" /></div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

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
            { id: 2, name: 'Jerry' }
        ])
        return {
            msg,
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