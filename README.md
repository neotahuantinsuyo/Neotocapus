<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NeoTocapu</title>
    
    <script src="https://aframe.io/releases/1.5.0/aframe.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/mind-ar@1.2.5/dist/mindar-image-aframe.prod.js"></script>

    <style>
        body { margin: 0; overflow: hidden; background-color: #000; }
        #cartel-guia { 
            position: absolute; top: 30px; left: 50%; transform: translateX(-50%); 
            background: rgba(0, 0, 0, 0.75); color: #00ffcc; padding: 12px 24px; 
            border-radius: 25px; font-family: sans-serif; font-size: 15px; 
            font-weight: bold; z-index: 9999; text-align: center; pointer-events: none; 
        }
    </style>
</head>
<body>

    <div id="cartel-guia">Apuntá con la cámara a tu NeoTocapu...</div>

    <a-scene mindar-image="imageTargetSrc: ./targetsnuevo.mind;" color-space="sRGB" renderer="colorManagement: true, physicallyCorrectLights" vr-mode-ui="enabled: false" device-orientation-permission-ui="enabled: false">
        
        <a-camera position="0 0 0" look-controls="enabled: false"></a-camera>

        <a-entity id="neotocapu-objetivo" mindar-image-target="targetIndex: 0">
            </a-entity>

    </a-scene>

    <script>
        const targetEl = document.querySelector('#neotocapu-objetivo');
        targetEl.addEventListener("targetFound", event => {
            alert("¡NeoTocapu Detectado con éxito!");
            // Redirección automática
            window.location.href = "https://fliphtml5.com/"; 
        });
    </script>

</body>
</html>
