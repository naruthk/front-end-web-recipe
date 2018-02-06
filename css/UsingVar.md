# Using var(--)

- You can do this `border-bottom: 10px solid var(--yellow);` if we define the following in our CSS file:
  ```css
  :root {
    --yellow: #ffc600;
    --black: #272727;
  }
  ```