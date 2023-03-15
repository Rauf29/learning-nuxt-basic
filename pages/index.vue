<template>
    <div>This is my main page</div>

    <Counter />
    <div>
        x: {{ x }}
        y: {{ y }}
    </div>
    <img src="img.png" alt="image">
</template>

<script setup>
const {x,y} = useMouse()
</script>