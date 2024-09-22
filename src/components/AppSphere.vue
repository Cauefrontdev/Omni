<template>
    <div ref="canvasContainer" class="canvas-container"></div>
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
        this.$refs.canvasContainer.appendChild(renderer.domElement);
  
        const geometry = new THREE.SphereGeometry(8, 32, 32);
        const wireframe = new THREE.WireframeGeometry(geometry);
        const lineMaterial = new THREE.LineBasicMaterial({ color: 0x6A0DAD });
        const wireframeMesh = new THREE.LineSegments(wireframe, lineMaterial);
        
        wireframeMesh.rotation.x = Math.PI / 20;
        scene.add(wireframeMesh);
  
        const light = new THREE.PointLight(0xffffff, 1);
        light.position.set(10, 10, 10);
        scene.add(light);
  
        camera.position.z = 15;
  
        const animate = () => {
          requestAnimationFrame(animate);
          wireframeMesh.rotation.y += 0.003; // Animação lenta
          wireframeMesh.position.y = Math.sin(Date.now() * 0.002) * 0.5; // Flutuação
          renderer.render(scene, camera);
        };
  
        animate();
      }
    }
  }
  </script>
  
  <style>
  .canvas-container {
    height: auto;
    display: flex;
    justify-content: center; 
    align-items: center;
    background-color: rgba(0, 0, 0, 0);
  }
  </style>
  