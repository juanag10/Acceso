# Acceso

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Acceso al micrófono</title>
</head>
<body>
    <h1>Grabación de audio</h1>
    <button id="start">Activar micrófono</button>
    <audio id="audio" controls></audio>
    <script>
        const startButton = document.getElementById('start');
        const audioElement = document.getElementById('audio');

        startButton.addEventListener('click', async () => {
            try {
                const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
                audioElement.srcObject = stream;
                audioElement.play();
            } catch (error) {
                console.error('Error al acceder al micrófono:', error);
            }
        });
    </script>
</body>
</html>
