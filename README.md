<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>❤️ Kalp</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #000;
    overflow: hidden;
}

.kalp {
    font-size: 120px;
    cursor: pointer;
    animation: nabiz 1s infinite;
}

@keyframes nabiz {
    0%, 100% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.2);
    }
}

.parca {
    position: absolute;
    font-size: 30px;
    pointer-events: none;
    animation: uc 1s forwards;
}

@keyframes uc {
    0% {
        opacity: 1;
        transform: translate(0, 0) scale(1);
    }

    100% {
        opacity: 0;
        transform: translate(var(--x), var(--y)) scale(0);
    }
}
</style>
</head>

<body>

<div class="kalp" onclick="kalbeBas()">❤️</div>

<script>
function kalbeBas() {
    for (let i = 0; i < 12; i++) {

        const parca = document.createElement("div");

        parca.className = "parca";
        parca.innerHTML = "❤️";

        parca.style.left = "50%";
        parca.style.top = "50%";

        parca.style.setProperty(
            "--x",
            (Math.random() * 300 - 150) + "px"
        );

        parca.style.setProperty(
            "--y",
            (Math.random() * 300 - 150) + "px"
        );

        document.body.appendChild(parca);

        setTimeout(() => {
            parca.remove();
        }, 1000);
    }
}
</script>

</body>
</html>
