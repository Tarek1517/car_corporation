<script setup>
const appConfig = useAppConfig()
</script>
<template>
    
<UApp :toaster="appConfig.toaster">
        <div class="w-full relative">
            <slot />
            
    </div>
</UApp>
</template>
<style scoped></style>
