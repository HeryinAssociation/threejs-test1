<template>
  <TresPerspectiveCamera :position="[3, 3, 3]" :fov="45" :look-at="[0, 0, 0]" />
  <!-- <OrbitControls /> -->
  <TresOrbitControls v-if="renderer" :args="[camera, renderer?.domElement]" />
  <TresMesh>
    <Suspense>
      <GLTFModel path="/models/3.glb" ref="modelRef" />
    </Suspense>
  </TresMesh>
  <!-- <TresDirectionalLight :position="[-4, 8, 4]" :intensity="1.5" cast-shadow /> -->
  <TresAmbientLight :intensity="5" />
</template>
<script lang="ts" setup>
import { extend, useTresContext } from "@tresjs/core";
import { GLTFModel } from "@tresjs/cientos";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls.js";

extend({ OrbitControls });
// const { scene } = await useGLTF("/models/test.glb");
const { renderer, camera } = useTresContext();
</script>
