- 👋 Hi, I’m @ThAlvys
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
ThAlvys/ThAlvys is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
extends Node2D

# Velocidade de movimento
var speed = 200
var velocity = Vector2.ZERO

func _process(delta):
    # Reseta a velocidade
    velocity = Vector2.ZERO

    # Detecta as teclas pressionadas
    if Input.is_action_pressed("ui_up"):
        velocity.y -= 1
    if Input.is_action_pressed("ui_down"):
        velocity.y += 1
    if Input.is_action_pressed("ui_left"):
        velocity.x -= 1
    if Input.is_action_pressed("ui_right"):
        velocity.x += 1

    # Normaliza o movimento e aplica a velocidade
    velocity = velocity.normalized() * speed
    position += velocity * delta
