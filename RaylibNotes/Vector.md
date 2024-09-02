Vector = Man har en lista på siffor som är mer än 1 siffra

2D spel = Vector av 2 tal.

```C
Vector(3,5);
```

Tradition i matte att döpa variabler till x y z:
```C
Vector(x, y); // 2D
Vector(x, y, z) // 3D
Vector(x, y, z, u, v) // 5D (lol)
```

Vector (3,5); 
```
-1 -2 -3 -4 -5
-2  \
-3   \
-4    \   
-5     *
```

Vector kan användas för position och velocity

position += velocity

Vector2.length() räknar ut längden av vektorn åt dig så du slipper använda trigonometri

Vector2.normalize();

Vector2.add(); Lägger till två vektorer

När man multiplicerar vektorer så brukar man ta vektorn och gångrar med ett vanligt tal

När man multiplicerar och dividerar så ska man se det som att vektorn förlängs

