<template>
   <TresCanvas window-size clear-color="#82dbc5">
    <TresPerspectiveCamera :position="[1, 1, 1]" />
    <OrbitControls />
    <Fit>
        <TresMesh v-for="(p, i) in positions" :key="i" :position="p">
            <TresBoxGeometry />
            <TresMeshNormalMaterial />
            <Html
                center
                transform
                :distance-factor="4"
            >
                <div class="card">
                    <div>
                        Hello
                    </div>
                </div>
            </Html>
        </TresMesh>
    </Fit>
   </TresCanvas>
</template>

<script setup lang="ts">
import { Html } from '@tresjs/cientos';

defineOptions({
    name: 'SomeBox',
});

const positions: number[][] = []
for (let y = 0; y <= 6; y += 2) {
  for (let x = 0; x <= 6; x += 2) {
    positions.push([1, x, y])
  }
}
// const { onLoop } = useRenderLoop();
// const boxRef = ref();

// onLoop(({ delta, elapsed }) => {
//     if (boxRef.value) {
//         boxRef.value.rotation.y += delta;
//         boxRef.value.rotation.z = elapsed * 0.2;
//     }
// })
</script>

<style>
.card-holder {
    display: flex;
    gap: 100px;
}

.card {
    width: 200px;
    height: 200px;
    background-color: red;
}
</style>