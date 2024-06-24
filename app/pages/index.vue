<template>
    <div id="container">
        <ClientOnly>
            <SomeBox />
        </ClientOnly>
    </div>
</template>

<script setup lang="ts">
defineOptions({
    name: 'IndexPage',
});
</script>