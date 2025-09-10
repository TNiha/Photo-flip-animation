<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Photo Flip Animation</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .flip-card {
            background-color: transparent;
            width: 300px;
            height: 400px;
            perspective: 1000px; /* 3D perspective */
        }

        .flip-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            text-align: center;
            transition: transform 0.8s;
            transform-style: preserve-3d;
        }

        .flip-card.is-flipped .flip-card-inner {
            transform: rotateY(180deg);
        }

        .flip-card-front, .flip-card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            -webkit-backface-visibility: hidden; /* For Safari */
            backface-visibility: hidden;
            border-radius: 1rem;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        .flip-card-front {
            background-color: #f3f4f6;
            color: black;
        }

        .flip-card-back {
            background-color: #1f2937;
            color: white;
            transform: rotateY(180deg);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
    </style>
</head>
<body class="bg-gray-100 flex flex-col items-center justify-center min-h-screen p-8 font-sans">

    <div class="text-center mb-8">
        <h1 class="text-4xl font-bold text-gray-800 mb-2">Photo Flip Cards</h1>
        <p class="text-lg text-gray-600">Click on any card to see the animation.</p>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">

        <!-- Photo Card 1 -->
        <div class="flip-card rounded-xl">
            <div class="flip-card-inner">
                <div class="flip-card-front">
                    <img src="https://placehold.co/300x400/2563eb/ffffff?text=Travel" alt="Travel" class="w-full h-full object-cover rounded-xl">
                </div>
                <div class="flip-card-back p-6 text-center">
                    <h2 class="text-2xl font-bold mb-2">Beautiful Scenery</h2>
                    <p class="text-gray-300">
                        A breathtaking view of mountains and a clear blue sky.
                        Perfect for a quiet getaway.
                    </p>
                </div>
            </div>
        </div>

        <!-- Photo Card 2 -->
        <div class="flip-card rounded-xl">
            <div class="flip-card-inner">
                <div class="flip-card-front">
                    <img src="https://placehold.co/300x400/be185d/ffffff?text=Cityscape" alt="Cityscape" class="w-full h-full object-cover rounded-xl">
                </div>
                <div class="flip-card-back p-6 text-center">
                    <h2 class="text-2xl font-bold mb-2">Urban Life</h2>
                    <p class="text-gray-300">
                        Vibrant city lights and towering skyscrapers.
                        The energy of the urban jungle.
                    </p>
                </div>
            </div>
        </div>

        <!-- Photo Card 3 -->
        <div class="flip-card rounded-xl">
            <div class="flip-card-inner">
                <div class="flip-card-front">
                    <img src="https://placehold.co/300x400/059669/ffffff?text=Nature" alt="Nature" class="w-full h-full object-cover rounded-xl">
                </div>
                <div class="flip-card-back p-6 text-center">
                    <h2 class="text-2xl font-bold mb-2">Peaceful Forest</h2>
                    <p class="text-gray-300">
                        An enchanted forest with lush greenery and a peaceful atmosphere.
                        A walk to remember.
                    </p>
                </div>
            </div>
        </div>

    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const cards = document.querySelectorAll('.flip-card');

            cards.forEach(card => {
                card.addEventListener('click', () => {
                    card.classList.toggle('is-flipped');
                });
            });
        });
    </script>
</body>
</html>
