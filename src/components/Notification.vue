<script setup>
import { computed } from 'vue';
let props = defineProps({
color: {
        type: String,
        required: false,
        validator(value, props) {
            return [
                'primary',
                'link',
                'info',
                'success',
                'warning',
                'danger',
                'white',
                'light',
                'dark',
                'text',
                'ghost',
            ].includes(value);
        }
    },
});

</script>
<template>
    <button class="notification" :class="classNames">
        <slot></slot>
    </button>
</template>