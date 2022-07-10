<template>
    <div><input v-model="msg" type="text" /></div>
    <div><input :value="msg" type="text" /></div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from 'vue';
import { ref } from 'vue';

export default defineComponent({
    setup() {
        let msg = ref<string>('hello webkit');
        interface Member {
            id: number,
            name: string
        };

        const userInfo = ref<Member>({
            id: 1,
            name: 'Tom'
        });

        return {
            msg,
            userInfo,
        };
    }
})
</script>

<style scoped>
.msg {
    font-size: 14px;
}
</style>