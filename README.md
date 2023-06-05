# SFML-Quick-Reference
A quick reference guide for the SFML library. This repository provides a collection of code snippets, examples, and explanations for the various features of SFML. Perfect for quick lookups and handy for both beginners and experienced SFML developers

## Window

```cpp
#include <SFML/Graphics.hpp>

sf::RenderWindow window(sf::VideoMode(width, height), "Title");
```


## Drawing Shapes

### Rectangle
```cpp
sf::RectangleShape rectangle(sf::Vector2f(width, height));
rectangle.setPosition(x, y);
rectangle.setFillColor(sf::Color::Red);
window.draw(rectangle);
```

### Circle
```cpp
sf::CircleShape circle(radius);
circle.setPosition(x, y);
circle.setFillColor(sf::Color::Blue);
window.draw(circle);
```

### Text
```cpp
sf::Font font;
if (!font.loadFromFile("font.ttf")) {
    // Handle font loading error
}

sf::Text text("Hello, SFML!", font, characterSize);
text.setPosition(x, y);
text.setFillColor(sf::Color::White);
window.draw(text);
```

### Input
```cpp
sf::Event event;
while (window.pollEvent(event)) {
    if (event.type == sf::Event::Closed) {
        window.close();
    }

    if (event.type == sf::Event::KeyPressed) {
        if (event.key.code == sf::Keyboard::Space) {
            // Handle space key press
        }
    }
}
```

### Sprites and Textures
```cpp
sf::Texture texture;
if (!texture.loadFromFile("image.png")) {
    // Handle texture loading error
}

sf::Sprite sprite(texture);
sprite.setPosition(x, y);
window.draw(sprite);
```

### Audio
```cpp
sf::SoundBuffer buffer;
if (!buffer.loadFromFile("sound.wav")) {
    // Handle sound loading error
}

sf::Sound sound(buffer);
sound.play();
```

### Time and Clock
```cpp
sf::Clock clock;

while (window.isOpen()) {
    sf::Time elapsed = clock.restart();
    float deltaTime = elapsed.asSeconds();

    // Use deltaTime for frame-rate independent updates
}
```

This cheat sheet provides a quick reference for commonly used SFML features. Feel free to customize and add more code snippets as needed.

For more detailed documentation and examples, refer to the [SFML official website](https://www.sfml-dev.org/).

Happy coding with SFML!
