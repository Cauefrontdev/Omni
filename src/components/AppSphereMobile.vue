<template>
  <div ref="canvasContainer" class="canvas-container2"></div>
</template>

<script>
import * as THREE from 'three';

export default {
name: 'AppSphere',
mounted() {
  this.createWireframeSphere();
},
methods: {
  createWireframeSphere() {
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(75, 500 / 500, 0.1, 1000);
    
    const renderer = new THREE.WebGLRenderer({ alpha: true });
    renderer.setSize(500, 500);
    renderer.shadowMap.enabled = true;
    renderer.shadowMap.type = THREE.PCFSoftShadowMap; // Sombra suave
    this.$refs.canvasContainer.appendChild(renderer.domElement);

    // Esfera oca com wireframe
    const geometry = new THREE.SphereGeometry(5, 32, 32);
    const wireframe = new THREE.WireframeGeometry(geometry);
    const lineMaterial = new THREE.LineBasicMaterial({ color: 0x6A0DAD });
    const wireframeMesh = new THREE.LineSegments(wireframe, lineMaterial);
    scene.add(wireframeMesh);

    // Luz ajustada para projetar sombra
    const light = new THREE.DirectionalLight(0xffffff, 1);
    light.position.set(10, 10, 5); // Posição ajustada para projetar sombra à direita
    light.castShadow = true;
    
    // Ajustes na sombra da luz
    light.shadow.mapSize.width = 1024;
    light.shadow.mapSize.height = 1024;
    light.shadow.camera.near = 0.5;
    light.shadow.camera.far = 50;
    light.shadow.camera.left = -10;
    light.shadow.camera.right = 10;
    light.shadow.camera.top = 10;
    light.shadow.camera.bottom = -10;
    scene.add(light);

    // Plano para receber a sombra
    const planeGeometry = new THREE.PlaneGeometry(500, 500);
    const planeMaterial = new THREE.ShadowMaterial({ opacity: 0.8 }); // Opacidade baixa para sombra suave
    const planeMesh = new THREE.Mesh(planeGeometry, planeMaterial);
    planeMesh.receiveShadow = true; // O plano recebe a sombra
    planeMesh.rotation.x = -Math.PI / 2;
    planeMesh.position.y = -8; // Posicionamento do plano
    scene.add(planeMesh);

    camera.position.z = 15;

    const animate = () => {
      requestAnimationFrame(animate);
      wireframeMesh.rotation.y += 0.003; // Animação lenta
      wireframeMesh.position.y = Math.sin(Date.now() * 0.002) * 0.5; // Efeito de flutuação
      renderer.render(scene, camera);
    };

    animate();
  }
}
}
</script>

<style>
.canvas-container2 {
  position: absolute;
  bottom: -400px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, 0);
}

@media (min-width: 750px) {
  .canvas-container2 {
    display: none;
  }
}

</style>
