<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AR Quadrilateral</title>
    <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
    <script src="https://cdn.rawgit.com/jeromeetienne/AR.js/2.0.8/aframe/build/aframe-ar.js"></script>
</head>
<body>
    <a-scene embedded arjs>
        <!-- Маркер A -->
        <a-marker preset="custom" type="pattern" url="path/to/markerA.patt">
            <a-box position="0 0.5 0" color="red"></a-box>
        </a-marker>

        <!-- Маркер B -->
        <a-marker preset="custom" type="pattern" url="path/to/markerB.patt">
            <a-box position="0 0.5 0" color="green"></a-box>
        </a-marker>

        <!-- Маркер C -->
        <a-marker preset="custom" type="pattern" url="path/to/markerC.patt">
            <a-box position="0 0.5 0" color="blue"></a-box>
        </a-marker>

        <!-- Маркер D -->
        <a-marker preset="custom" type="pattern" url="path/to/markerD.patt">
            <a-box position="0 0.5 0" color="yellow"></a-box>
        </a-marker>

        <!-- Камера -->
        <a-entity camera></a-entity>
    </a-scene>

    <script>
        AFRAME.registerComponent('calculate-quadrilateral', {
            init: function () {
                // Отримуємо координати точок A, B, C, D
                var markerA = document.querySelector("[url='path/to/markerA.patt']");
                var markerB = document.querySelector("[url='path/to/markerB.patt']");
                var markerC = document.querySelector("[url='path/to/markerC.patt']");
                var markerD = document.querySelector("[url='path/to/markerD.patt']");

                var positionA = markerA.object3D.position;
                var positionB = markerB.object3D.position;
                var positionC = markerC.object3D.position;
                var positionD = markerD.object3D.position;

                // Виведення координат точок
                console.log("A:", positionA);
                console.log("B:", positionB);
                console.log("C:", positionC);
                console.log("D:", positionD);

                // Розрахунок та виведення периметра
                var perimeter = distance(positionA, positionB) + distance(positionB, positionC) +
                                distance(positionC, positionD) + distance(positionD, positionA);
                console.log("Perimeter:", perimeter);

                // Розрахунок та виведення площі трикутників ABC та ACD
                var areaABC = calculateTriangleArea(positionA, positionB, positionC);
                var areaACD = calculateTriangleArea(positionA, positionC, positionD);
                console.log("Area of ABC:", areaABC);
                console.log("Area of ACD:", areaACD);
            }
        });

        function distance(p1, p2) {
            return Math.sqrt(Math.pow(p2.x - p1.x, 2) + Math.pow(p2.y - p1.y, 2) + Math.pow(p2.z - p1.z, 2));
        }

        function calculateTriangleArea(p1, p2, p3) {
            var a = distance(p1, p2);
            var b = distance(p2, p3);
            var c = distance(p3, p1);
            var s = (a + b + c) / 2;
            return Math.sqrt(s * (s - a) * (s - b) * (s - c));
        }
    </script>

    <a-entity calculate-quadrilateral></a-entity>
</body>
</html>
